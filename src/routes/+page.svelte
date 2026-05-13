<script>
	import Header from '../components/Header.svelte';
	import Main from '../components/Main.svelte';
	import Step from '../components/Step.svelte';
	import Footer from '../components/Footer.svelte';
	import Step2 from '../components/Step2.svelte';
	import ProjectGrid from '../components/ProjectGrid.svelte';
	import ProjectCard from '../components/ProjectCard.svelte';
	import OtherProjectGrid from '../components/OtherProjectGrid.svelte';
</script>

<Header />

<Main />

<Step2 id="about" title="About Me">
	<div class="flex flex-col gap-6 md:flex-row">
		<p class="md:w-1/2">
			I’m Presley Smith, a recent <strong>Rochester Institute of Technology</strong> graduate with a
			Bachelor of Science in New Media Interactive Development. I’m passionate about building
			interactive and creative digital experiences across web development, software engineering, and
			emerging technologies. Over the past few years, I’ve worked on everything from full stack web
			applications and game projects to IoT and hardware based systems through coursework,
			<strong>hackathons, internships, and personal projects.</strong>
		</p>

		<p class="md:w-1/2">
			I’ve collaborated on team based development projects, participated in hackathons like
			BrickHack and WiCHacks, and built projects using technologies like <strong>React, Node.js, MongoDB,
			Python, C#, and Arduino based hardware.</strong> I enjoy solving problems, learning new technologies,
			and creating things that feel both functional and engaging for users. 
            <br>
            <br>
            Right now, I’m focused on continuing to grow as a developer while exploring opportunities in software engineering,
			web development, interactive media, and creative technology. Feel free to check out my work
			below and see what I’ve been building.
		</p>
	</div>
</Step2>

<Step id="showcase" title="Showcase">
	<p>Projects I've Worked On</p>
	<br />
	<ProjectGrid />
</Step>

<Step id="projects" title="Other Projects">
	<p>More project cards or links.</p>
	<br />
	<OtherProjectGrid />
</Step>

<Footer />
