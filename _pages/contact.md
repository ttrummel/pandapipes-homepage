---
layout: single
title: Contact
permalink: /contact/
author_profile: true
classes:
  - wide
developers:
  - name: "Dennis Cronbach"
    nickname: Dennis
    email: dennis.cronbach@iee.fraunhofer.de
    image: "/images/contact/Cronbach.PNG"
    text: 
  - name: "Daniel Lohmeier"
    nickname: Daniel
    email: daniel.lohmeier@iee.fraunhofer.de
    image: "/images/contact/Lohmeier.jpg"
    text: 
  - name: "Simon Ruben Drauz"
    nickname: Simon
    email: simon.ruben.drauz@iee.fraunhofer.de
    image: "/images/contact/Drauz.png"
    text: 
  - name: "Tanja Kneiske"
    nickname: Tanja
    email: tanja.kneiske@iee.fraunhofer.de
    image: "/images/contact/Kneiske.png"
    text: 
  - name: "Martin Braun"
    nickname: Martin Braun
    email: martin.braun@uni-kassel.de
    image: "/images/contact/Braun.jpg"
    text: "is strategically guiding and paving the way towards new fields of application."    
---
<p></p>

## Mailing List <a name="list"></a>
If you want to receive updates about new versions and other news about pandapipes, you can subscribe to the pandapipes mailing list:

[<i class='fas fa-envelope'></i> Subscribe](mailto:sympa@fraunhofer.de?subject=subscribe%20pandapower){: .btn .btn--success .btn--large}<br>
<small>If you no longer want to receive updates, <a href="mailto:sympa@fraunhofer.de?subject=unsubscribe%20pandapipes">unsubscribe here</a>.</small>

## About us

pandapipes is a development by the Division for Grid Planning and Grid Operation at the Fraunhofer Institute for Energy Economics and Energy System Technology (IEE), Kassel with support by the research group Energy Management and Power System Operation, University of Kassel.


[<img src="https://www.uni-kassel.de/eecs/fileadmin/datas/fb16/Fachgebiete/energiemanagement/iee.png">](https://www.iee.fraunhofer.de/en.html)
[<img src="https://www.uni-kassel.de/eecs/fileadmin/datas/fb16/Fachgebiete/energiemanagement/e2n.png">](https://www.uni-kassel.de/eecs/en/fachgebiete/e2n/home.html)


## Who we are

And these are some of the people behind pandapipes:

<div class="authors">
  {% for developer in page.developers %}
    <p>
    <img style="padding:2px 2px 2px 2px;  margin-right: 15px" src="{{ developer.image | relative_url }}" width="120" align="left"/> 
    <span style="margin-top: -5px; display:inline-block; max-width:500px;">
        <b>{{ developer.name }}</b> {{ developer.text }} <br>
        <a href="mailto:{{developer.email}}">Contact {{developer.nickname}}</a> 
    </span>
    <BR CLEAR="left"/> 
    </p>
  {% endfor %}
</div>

[See Full List of authors and contributors](https://pandapipes.readthedocs.io/en/latest/about/authors.html){: .btn .btn--success .btn--large}

## Impressum

### Adress

Fraunhofer Institute for Energy Economics and Energy System Technology IEE<br>
Grid Planning and Grid Operation Department<br>
Prof. Dr.-Ing. Martin Braun<br>
Koenigstor 59<br>
34119 Kassel<br>

### Copyright und Liability 

The layout of the homepage, the graphics it contains, as well as the collection of documents are protected by copyright. Reproduction of these pages is authorized exclusively for personal use, no alterations are permitted, and any reproduced material may not be disseminated or displayed in public. All individual documents are likewise protected by copyright. All information on this server is provided without guarantee as to its accuracy. Under no circumstances will liability be assumed for loss or damage sustained through use of the information provided. Despite thorough control we do not take liability upon the content and correctness of external links. The operators respectively the authors are solely responsible for the linked web sides and publications. 
