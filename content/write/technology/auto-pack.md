---
title: "Auto Pack"
date: 2023-05-05
description: "packaging and publishing on gitlab components"
tags: ["technology"]
categories: ["technology"]
---
The program is written in python language, pyinstall generates executable files for windows platform, and nsis package program. Gitlab CI pushes tag and release. All are implemented using gitlab components.

## first

Dockerizing. Let’s play with docker, write two dockerfile to fit gitlab ci and personal environment dependence.The location and name of these two files are: py3\_win64\_ins.df, nsis.df

## second

GitLab CI.Make our pipeline. Build image and push it into `GitLab Container Registry`. Use pyinstall and nsis image generates executable and package file, the name is `main.exe` and `apc-win64-v1.0.0.exe`. These files are saved in the artifacts.Upload `apc-win64-v1.0.0.exe` file to `GitLab Package Registry`. Final push `Tags` and `Releases` on GitLab repo.

## epilogue

It was implemented here [https://gitlab.com/NJ2046/auto\_pack](https://gitlab.com/NJ2046/auto_pack)

## reference

-   [https://github.com/cdrx/docker-pyinstaller](https://github.com/cdrx/docker-pyinstaller)
-   [https://github.com/Schnouki/docker-pyinstaller-ci](https://github.com/Schnouki/docker-pyinstaller-ci)
-   [https://github.com/binfalse/docker-nsis](https://github.com/binfalse/docker-nsis)
-   [https://gitlab.com/gitlab-org/gitlab/-/issues/36133](https://gitlab.com/gitlab-org/gitlab/-/issues/36133)
