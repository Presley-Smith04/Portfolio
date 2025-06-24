<script>
    import Header from "../components/Header.svelte";
    import Main from "../components/Main.svelte";
    import Step from "../components/Step.svelte";
    import Footer from "../components/Footer.svelte";
    import Step2 from "../components/Step2.svelte";
    import ProjectGrid from "../components/ProjectGrid.svelte";
    import ProjectCard from "../components/ProjectCard.svelte";
    import OtherProjectGrid from "../components/OtherProjectGrid.svelte";
</script>

<Header />

<Main />

<Step2 id="about" title="About Me">
    <div class="flex flex-col md:flex-row gap-6">
        <p class="md:w-1/2">
            I’m Presley Smith, a passionate and driven New Media Interactive
            Development student at the <strong
                >Rochester Institute of Technology</strong
            >, entering my fourth year. Originally from a small town in New
            York, I discovered my love for coding early and have expanded my
            skills through self-directed learning, online courses, and hands-on
            projects. Throughout my time at RIT, I’ve collaborated on numerous
            game development projects, participated in hackathons like
            <strong>BrickHack 25</strong>, and contributed to the
            <strong>Echoes VIP website</strong>. These experiences have
            strengthened both my technical and teamwork skills.
        </p>

        <p class="md:w-1/2">
            Currently, I’m focused on building meaningful and engaging web
            applications using tools like React, Node.js, and MongoDB. I’m
            always learning, whether it’s exploring new technologies or
            improving my design and development workflow. I’m excited to apply
            my skills in a professional setting and keep growing through
            hands-on experience.
            <br /><br />
            Feel free to explore my projects below — I’m excited to share what I’ve
            built and the directions I’m heading next!
        </p>
    </div>
</Step2>



<Step id="showcase" title="Showcase">
    <p>Projects I've Worked On</p>
    <br>
    <ProjectGrid />
</Step>



<Step id="projects" title="Other Projects">
    <p>More project cards or links.</p>
    <br>
    <OtherProjectGrid />
</Step>






<Footer />
