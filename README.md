<!-- banner-->
![img alt](https://github.com/Shaifuzzman-Ratul/Shaifuzzman-Ratul/blob/f2602aa6e783d4cd188fa9200596c5888b640d72/gitgub-banner.png)
<!-- About me -->
<h1 align="center">Hi 👋, I'm Md Shaifuzzman Ratul</h1>
<h3 align="center">Learning MERN Stack • Code. Debug. Learn. Repeat.</h3>
<h2> 👋 ABOUT ME</h2>
I’m a passionate 'MERN Stack learner' and aspiring Full-Stack Developer.  
I love building web applications, solving problems with code, and learning new technologies every day.

- 💻 Currently exploring **Next.js** and **React Native**  
- 🛠️ Working on a **e commerce website project**  
- 🌱 Learning **node.js,express.js,mongodb**  
- 🎨 Skilled in **HTML, CSS, Tailwind CSS, JavaScript, React, Firebase**  

I enjoy collaborating on projects, contributing to open-source, and sharing knowledge with the community.
<br/>
<p align="left"> <img src="https://komarev.com/ghpvc/?username=shaifuzzman-ratul&label=Profile%20views&color=0e75b6&style=flat" alt="shaifuzzman-ratul" /> </p>

<br/>
<!--connect with me -->
<h2>CONNECT WITH ME</h2>

[![Facebook](https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge&logo=facebook&logoColor=white)](https://www.facebook.com/ra.tul.35380)
[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://www.instagram.com/ra_tul99/)
[![X](https://img.shields.io/badge/X-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/yourusername)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:your.email@example.com)
<br/><br/><br/>


<!-- technology stack -->
## <img src="https://media4.giphy.com/media/KGhpQ5NMoWKQurlHwI/giphy.webp" width="35"> **TECHNOLOGY STACK**

| **Fontend & Languages** | **CSS Frameworks & Libraries** | **JS Frameworks & Libraries** | **Databases** |
|---------------|-------------------------------|-------------------------------|-------------------|
| ![HTML](https://skillicons.dev/icons?i=html) ![CSS](https://skillicons.dev/icons?i=css)  ![JavaScript](https://skillicons.dev/icons?i=javascript) |   ![Tailwind](https://skillicons.dev/icons?i=tailwind) | ![React](https://skillicons.dev/icons?i=react) ![Node.js](https://skillicons.dev/icons?i=nodejs) ![Express](https://skillicons.dev/icons?i=express) | ![MongoDB](https://skillicons.dev/icons?i=mongodb) ![Firebase](https://skillicons.dev/icons?i=firebase) |

| **Deployment Platforms** | **Design & Graphics** | **Tools & Technologies** |
|--------------------------|--------------------|-------------------------|
| ![Vercel](https://skillicons.dev/icons?i=vercel) ![Netlify](https://skillicons.dev/icons?i=netlify) ![Firebase](https://skillicons.dev/icons?i=firebase) | ![Figma](https://skillicons.dev/icons?i=figma) ![Pixo](https://skillicons.dev/icons?i=pixo)| ![Windows](https://skillicons.dev/icons?i=windows)  ![GitHub](https://skillicons.dev/icons?i=github) ![VSCode](https://skillicons.dev/icons?i=vscode) ![Postman](https://skillicons.dev/icons?i=postman) |

<br/><br/>
<!-- github statistics -->
<h2>GITHUB STATISTICS</h2> 
<p><img align="left" src="https://github-readme-stats.vercel.app/api/top-langs?username=shaifuzzman-ratul&show_icons=true&locale=en&layout=compact" alt="shaifuzzman-ratul" /></p>
<p>&nbsp;<img align="center" src="https://github-readme-stats.vercel.app/api?username=shaifuzzman-ratul&show_icons=true&locale=en" alt="shaifuzzman-ratul" /></p>
<br/><br/>
<!-- repository stact& streak -->
<h2>REPOSITORY STATS & STREAK<h2/>

<p><img align="center" src="https://github-readme-streak-stats.herokuapp.com/?user=shaifuzzman-ratul&" alt="shaifuzzman-ratul" /></p>


snkae


# GitHub Action for generating a contribution graph with a snake eating your contributions.

name: Generate Snake

# Controls when the action will run. This action runs every 6 hours.

on:
  schedule:
      # every 6 hours
    - cron: "0 */6 * * *"

# This command allows us to run the Action automatically from the Actions tab.
  workflow_dispatch:

# The sequence of runs in this workflow:
jobs:
  # This workflow contains a single job called "build"
  build:
    # The type of runner that the job will run on
    runs-on: ubuntu-latest

    # Steps represent a sequence of tasks that will be executed as part of the job
    steps:

    # Checks repo under $GITHUB_WORKSHOP, so your job can access it
      - uses: actions/checkout@v2

    # Generates the snake  
      - uses: Platane/snk@master
        id: snake-gif
        with:
          github_user_name:Shaifuzzman-Ratul 
          # these next 2 lines generate the files on a branch called "output". This keeps the main branch from cluttering up.
          gif_out_path: dist/github-contribution-grid-snake.gif
          svg_out_path: dist/github-contribution-grid-snake.svg

     # show the status of the build. Makes it easier for debugging (if there's any issues).
      - run: git status

      # Push the changes
      - name: Push changes
        uses: ad-m/github-push-action@master
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          branch: master
          force: true

      - uses: crazy-max/ghaction-github-pages@v2.1.3
        with:
          # the output branch we mentioned above
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
