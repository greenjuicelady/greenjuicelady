## Hi there 👋

![HTML](https://ziadoua.github.io/m3-Markdown-Badges/badges/HTML/html2.svg)
![CSS](https://ziadoua.github.io/m3-Markdown-Badges/badges/CSS/css2.svg)
![C#](https://ziadoua.github.io/m3-Markdown-Badges/badges/CSharp/csharp2.svg)
![ILLUSTRATOR](https://ziadoua.github.io/m3-Markdown-Badges/badges/Illustrator/illustrator2.svg)
![PHOTSHOP](https://ziadoua.github.io/m3-Markdown-Badges/badges/Photoshop/photoshop2.svg)


![Anurag's GitHub stats](https://github-readme-stats.vercel.app/api?username=anuraghazra&show_icons=true&theme=radical)


<div align="center">
  
⚡**Tech Stack**⚡<br>
<img src="https://img.shields.io/badge/JAVA-1E8CBE?style=flat-square"/>
<img src="https://img.shields.io/badge/Spring-6DB33F?style=flat-square&logo=spring&logoColor=white"/>
<img src="https://img.shields.io/badge/Spring Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white"/>
<img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white"/>
<img src="https://img.shields.io/badge/Vue.js-4FC08D?style=flat-square&logo=vuedotjs&logoColor=white"/>
<img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=000000"/>
<img src="https://img.shields.io/badge/CSS-1572B6?style=flat-square&logo=css3&logoColor=white"/>

🚀**Soft Skills**🚀<br>
<img src="https://img.shields.io/badge/Figma-F24E1E?style=flat-square&logo=figma&logoColor=white"/>
<img src="https://img.shields.io/badge/Adobe XD-FF61F6?style=flat-square&logo=adobexd&logoColor=white"/>
<img src="https://img.shields.io/badge/Adobe Photoshop-31A8FF?style=flat-square&logo=adobephotoshop&logoColor=white"/>
<img src="https://img.shields.io/badge/Adobe Illustrator-FF9A00?style=flat-square&logo=adobeillustrator&logoColor=white"/>

</div>

<br>
<br>
<br>
<br>
This GitHub Action creates a GitHub contribution calendar on a 3D profile image.

## How to use (GitHub Actions)
## How to use (GitHub Actions) - Basic

This action generate your github profile 3d contribute calendar and make a commit to your repo.
You can also trigger action by yourself after add this action.
@@ -130,6 +130,10 @@ e.g.
![](./profile-3d-contrib/profile-green-animate.svg)
```

## How to use (GitHub Actions) - Advanced examples
#### [More info in EXAMPLES.md](./EXAMPLES.md)
## How to use (local)

Set the `GITHUB_TOKEN` environment variable to the value of "personal access token".
@@ -151,106 +155,6 @@ npm run build
node . USER_NAME
```

## Advanced example: automatic day/night switching + keeping output in other branch
This alternative workflow generates two files, `day.svg` and `night.svg`, and pushes it to `output-3d-contrib` branch, keeping the main repo 'clean' from build artifacts.
### step 1. Create special repository ([see above](#step-1-create-special-repository))
### step 2. Create `conf/github-profile-3d-contrib.json` file in your <username> repo:
```json:conf/github-profile-3d-contrib.json
[
    {
        "type": "normal",
        "fileName": "day.svg",
        "backgroundColor": "#ffffff",
        "foregroundColor": "#00000f",
        "strongColor": "#111133",
        "weakColor": "gray",
        "radarColor": "#47a042",
        "growingAnimation": true,
        "contribColors": [
            "#efefef",
            "#d8e887",
            "#8cc569",
            "#47a042",
            "#1d6a23"
        ]
    },
    {
        "type": "rainbow",
        "fileName": "night.svg",
        "backgroundColor": "#00000f",
        "foregroundColor": "#eeeeff",
        "strongColor": "rgb(255,200,55)",
        "weakColor": "#aaaaaa",
        "radarColor": "rgb(255,200,55)",
        "growingAnimation": true,
        "saturation": "50%",
        "contribLightness": [
            "20%",
            "30%",
            "35%",
            "40%",
            "50%"
        ],
        "duration": "10s",
        "hueRatio": -7
    }
]
```
### step 3. Create `.github/workflows/profile-3d-contrib.yml` workflow file in your <username> repo:
```yaml:.github/workflows/profile-3d-contrib.yml
name: generate 3d chart for profile contributions
on:
  # run automatically every 24 hours
  schedule:
    - cron: "0 */24 * * *" 
  
  # allows to manually run the job at any time
  workflow_dispatch:
  
  # run on every push on the main branch
  # don't forget to change if you're using 'master' branch
  push:
    branches:
    - main
jobs:
  build:
    runs-on: ubuntu-latest
    name: generate-github-profile-3d-contrib
    steps:
      - uses: actions/checkout@v3
      - uses: yoshi389111/github-profile-3d-contrib@0.7.1
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          USERNAME: ${{ github.repository_owner }}
          SETTING_JSON: conf/github-profile-3d-contrib.json
          
      # push the content of <build_dir> to a branch
      # the content will be available at https://raw.githubusercontent.com/<github_user>/<repository>/<target_branch>/<file> , or as github page
      - name: push SVGs to the output-3d branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output-3d-contrib
          build_dir: profile-3d-contrib
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```
### step 4. Edit `README.md` in your <username> repo, adding the following code:
Do not forget to replace `<github_user>` and `<repository>` with your GitHub username.
```html
<p align="center" >
	<picture>
	  <source media="(prefers-color-scheme: dark)"  srcset="https://raw.githubusercontent.com/<github_user>/<repository>/output-3d-contrib/night.svg" />
	  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/<github_user>/<repository>/output-3d-contrib/day.svg" />
	  <img alt="github profile contributions chart"    src="https://raw.githubusercontent.com/<github_user>/<repository>/output-3d-contrib/day.svg" />
	</picture>
</p>
```

## Licence


🔭 I’m currently working on ...
🌱 I’m currently learning ...
👯 I’m looking to collaborate on ...
🤔 I’m looking for help with ...
💬 Ask me about ...
📫 How to reach me: ...
😄 Pronouns: ...
⚡ Fun fact: ...
