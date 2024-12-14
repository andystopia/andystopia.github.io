<script lang="ts">
	import { Github, Linkedin, Mail, Phone } from 'lucide-svelte';
	import '../app.css';

	let liameObsc = 'zxbupx.xyxvwnxzxtx@x4x0xlxnxqxzxjxrxexqxannk';
	let liameRendered = $state(false);
	function rot13(str: string) {
		return str.replace(/[a-z]/gi, (c) =>
			String.fromCharCode(c.charCodeAt(0) + (c.toLowerCase() < 'n' ? 13 : -13))
		);
	}

  function computeEmail(rend: boolean) {
    if (rend) {
      return rot13(liameObsc)
						.split('')
						.map((v, i) => [v, i])
						.filter((x) => x[1] % 2 == 0)
						.map((x) => x[0])
						.reverse()
						.join('')
    } else { 
      return liameObsc
    }
  }
</script>

<div
	class="w-screen h-screen from-zinc-800 to-zinc-700 bg-gradient-to-tr text-white grid items-center grid-rows-[5fr_1fr]"
>
	<div class="max-w-full pl-10 md:pl-32">
		<h1 class="font-semibold text-1xl italic text-zinc-300">Portfolio Of</h1>
		<h1 class="font-black text-7xl">Andy Day</h1>
		<h2 class="mt-2">A Statistician and Software Engineer</h2>

		<button
			class="bg-orange-700 font-semibold px-5 py-2 rounded-full mt-10 ml-2 shadow transform hover:scale-[1.025] transition-transform duration-[25ms] active:scale-100 justify-between flex flex-row gap-x-3 border-2 border-orange-700 hover:border-orange-600 text-sm"
			onclick={() => window.scrollTo({ top: window.innerHeight, behavior: 'smooth' })}
			><div class="text-nowrap">Let's Get Into It!</div>
			<div>&#8595;</div></button
		>
	</div>
	<div class=" px-10 grid place-items-center">
		<div class="h-full py-5">
			<h3 class="font-thin text-xl text-zinc-200 mb-2 text-center">Contacts</h3>
			<div class="grid grid-cols-3 gap-y-2 gap-x-5 h-25 place-items-center max-w-lg font-thin">
				<button
					class="px-5 py-2 rounded-md place-items-center grid bg-white/5 w-full shadow transition-colors duration-75 hover:border-zinc-600 border border-transparent"
          onclick={() => liameRendered = !liameRendered}
				>
					<Mail strokeWidth={1} stroke="#e0e0e0" />
					<div class="">Email</div>
				</button>
				<a
					href="https://www.linkedin.com/in/andrew-day-7a588629a/"
					class="px-5 py-2 rounded-md place-items-center grid bg-white/5 w-full shadow transition-colors duration-75 hover:border-zinc-600 border border-transparent"
					target="_blank"
					rel="noopener noreferrer"
				>
					<Linkedin strokeWidth={1} stroke="#e0e0e0" />
					<div class="">LinkedIn</div>
				</a>
				<a
					href="https://github.com/andystopia"
					target="_blank"
					rel="noopener noreferrer"
					class="px-5 py-2 rounded-md place-items-center grid bg-white/5 w-full shadow transition-colors duration-75 hover:border-zinc-600 border border-transparent"
				>
					<Github strokeWidth={1} stroke="#e0e0e0" />
					<div class="">GitHub</div>
				</a>
			</div>
		</div>
	</div>
	{#if liameRendered}
		<div class="grid place-items-center py-4">
			<div class="w-80 h-16 border-zinc-700 border rounded-md px-4 py-2">
				<div class="mb-2">My Email Is</div>
				<code class="bg-white/10 w-full px-10 py-1">
          {computeEmail(liameRendered)}
				</code>
			</div>
		</div>
	{/if}
</div>

<div
	class="bg-neutral-800 border-t-2 border-orange-500 text-neutral-100 px-5 py-20 grid place-items-center"
>
	<div class="mx-5 max-w-[45em]">
		<h2 class="text-4xl font-semibold underline decoration-orange-500 pb-10">Introduction.</h2>
		<div class="font-serif indent-4">
			<p class="text-justify text-balance">
				I am an avid stastistian and computer scientist. I really enjoy architecting large
				solutions, composing them from smaller parts that I've both written myself and those written
				in collaboration with team members. I seek to use my computer science and statistics
				knowledge to form complex machine learning and data driven, impactful decisions.
			</p>
			<p class="text-justify text-balance">
				I <emph>actively</emph> develop solutions across high and low level languages, and enjoy creating
				anything from web dashboards, data pipelines, migrations, backend REST APIs, and scripting. I
				really enjoy building highly integrated, reliable systems that are maintainable and will last.
			</p>
		</div>
	</div>
</div>

<div
	class="from-zinc-800 to-zinc-900 bg-gradient-to-tr border-t-2 border-orange-500 text-neutral-100 px-5 py-20 grid place-items-center"
>
	<div class="mx-5 max-w-[45em] w-full">
		<h2 class="text-4xl font-semibold underline decoration-orange-500 mb-10">Showcase.</h2>
	</div>
	<div class="pb-2">All Projects Written <emph class="italic">Exclusively</emph> By Me</div>
	<div class="flex gap-y-4 flex-col">
		<div
			class="flex lg:flex-row flex-col-reverse lg:px-10 from-purple-800 to-purple-600 via-purple-800 bg-gradient-to-l rounded-md"
		>
			<div class="flex-grow w-full pt-6 pl-8 mb-8 pr-8">
				<h3 class="font-bold text-3xl mb-4">Newt</h3>
				<p class="indent-4 text-sm">
					Newt is a package manager search tool. It's designed to start instantly, search
					perfomantly, and provide a smoother developer experience than web based tools.
				</p>
				<h4 class="font-bold text-lg mt-4">Features</h4>
				<ol class="ml-4">
					<li class="list-disc">Instant Startup</li>
					<li class="list-disc">Rendered Natively on the GPU</li>
					<li class="list-disc">Excellent Speed From Multithreading</li>
					<li class="list-disc">Integrates a complex ecosystem into one tool</li>
					<li class="list-disc">Used on the daily by myself.</li>
				</ol>
			</div>
			<img src="./newt-screenshot.png" alt="Newt Screenshot" class="w-full" />
		</div>

		<div
			class="flex lg:flex-row flex-col-reverse lg:px-10 from-purple-800 to-purple-600 via-purple-800 bg-gradient-to-l rounded-md"
		>
			<div class="flex-grow w-full pt-6 pl-8 mb-8 pr-8">
				<h3 class="font-bold text-3xl mb-4">Lichen Maps</h3>
				<p class="indent-4 text-sm">
					Lichen Maps is a full stack web application that I wrote, which uses OpenLayers for
					rendering, supports multiple map views, can give the user the weather from weather.gov,
					and processes OpenStreetMap data files with a custom, handwritten geocoder, with a
					Meilisearch (like Elasticsearch) search backend. I multithreaded a OSM file format
					decoder, for a 10x performance improvement compared to the open source library. I feel
					this project displays the GIS proficiency and full stack web development experience that I
					could bring to a team.
				</p>
				<h4 class="font-bold text-lg mt-4">Skills</h4>
				<ol class="ml-4">
					<li class="list-disc">Deployable with one command.</li>
					<li class="list-disc">Custom Written Geocoder</li>
					<li class="list-disc">Javascript and SolidJS frontend.</li>
					<li class="list-disc">Analytics in backend done with R and DuckDB</li>
					<li class="list-disc">Uses: SQlite, DuckDB, and Postgres/PostGIS</li>
				</ol>
			</div>
			<div class="w-full px-4 py-4 grid place-items-center">
				<img
					src="./lichen-screenshot.png"
					alt="Newt Screenshot"
					class="w-full rounded-md shadow-md shadow-black"
				/>
			</div>
		</div>
		<div
			class="flex lg:flex-row flex-col-reverse lg:px-10 from-purple-800 to-purple-600 via-purple-800 bg-gradient-to-l rounded-md"
		>
			<div class="flex-grow w-full pt-6 pl-8 mb-8 pr-8">
				<h3 class="font-bold text-3xl mb-4">Election Simulator</h3>
				<p class="indent-4 text-sm">
					I wrote this, because I wanted to know more about how the election would likely turn out.
					I believe it nicely, and succiently demonstrates my data visualization skills, my ability
					to cleanly convey information, and my ability to design beautiful UIs.
				</p>
				<h4 class="font-bold text-lg mt-4">Skills</h4>
				<ol class="ml-4">
					<li class="list-disc">d3 visualization</li>
					<li class="list-disc">Statistical Modeling (stochastic)</li>
					<li class="list-disc">Svelte / JS frontend only page</li>
				</ol>
			</div>
			<div class="w-full px-4 py-4 grid place-items-center grid-cols-3">
				<img
					src="./tossup.png"
					alt="Newt Screenshot"
					class="w-full rounded-md shadow-md shadow-black"
				/>
				<img
					src="./roll.png"
					alt="Newt Screenshot"
					class="w-full rounded-md shadow-md shadow-black"
				/>
				<img
					src="./pretty-ui.png"
					alt="Newt Screenshot"
					class="w-full rounded-md shadow-md shadow-black"
				/>
			</div>
		</div>
		<a href="https://github.com/andystopia" class="text-center underline"
			>There's A LOT more on my GitHub, including Open Source Software!</a
		>
	</div>
</div>

<div
	class="from-zinc-800 to-neutral-800 bg-gradient-to-tr border-t-2 border-orange-500 text-neutral-100 px-5 py-20 grid place-items-center"
>
	<div class="mx-5 max-w-[45em] w-full">
		<h2 class="text-4xl font-semibold underline decoration-orange-500 mb-10">
			Cool, but can you write technical documentation?
		</h2>

		<a href="https://andystopia.github.io/diffeqrxn-docs" class="underline"
			>I can, I do, and I enjoy it!</a
		> Here's a link to user documentation for a project that I created for my bachelors thesis. It is
		a domain specific tool; however. I hope to publish more independent pieces soon!
	</div>
</div>

<div
	class="from-zinc-800 to-neutral-800 bg-gradient-to-tr border-t-2 border-orange-500 text-neutral-100 px-5 py-20 grid place-items-center"
>
	<div class="mx-5 max-w-[45em] w-full">
		<h2 class="text-4xl font-semibold mb-10">We're looking to hire someone like you!</h2>

		I would love to hear what you're creating! Drop me a line at any of my contacts :)

		<div class="flex justify-center">
			<button
				class="bg-orange-700 font-semibold px-5 py-2 rounded-full mt-10 ml-2 shadow transform hover:scale-[1.025] transition-transform duration-[25ms] active:scale-100 justify-between flex flex-row gap-x-3 border-2 border-orange-700 hover:border-orange-600 text-sm"
				onclick={() => window.scrollTo({ top: 0, behavior: 'smooth' })}
				><div class="text-nowrap">Contacts</div>
				<div>&#8593;</div></button
			>
		</div>
	</div>
</div>
