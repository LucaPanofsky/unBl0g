---
title: "{{ replace .Name "-" " " | title }}"
date: {{ .Date }}
author: Luca Panofsky
draft: false
year: "{{ dateFormat "2006" .Date }}"
month: "{{ dateFormat "2006/01" .Date }}"
---
