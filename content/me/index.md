---
eleventyExcludeFromCollections: true
layout: page.njk
title: About me
---

<script src="//code.jquery.com/jquery.js"></script>
<style>
.node {
  stroke: #fff;
  stroke-width: 1.5px;
}
.link {
  stroke: #999;
  stroke-opacity: .6;
}
</style>
<div id='d3div'></div>
<script src="//d3js.org/d3.v3.min.js"></script>
<script>
var width = $("#d3div").width(),
    height = 400;
var color = d3.scale.category20();
var force = d3.layout.force()
    .charge(-62)
    .linkDistance(80)
    .size([width, height]);
var svg = d3.select("#d3div").append("svg")
    .attr("width", width)
    .attr("height", height);
d3.json("/assets/data/jazz.json", function(error, graph) {
  if (error) throw error;
  force
      .nodes(graph.nodes)
      .links(graph.links)
      .start();
  var link = svg.selectAll(".link")
      .data(graph.links)
    .enter().append("line")
      .attr("class", "link")
      .style("stroke-width", function(d) { return Math.sqrt(d.value); });
  var node = svg.selectAll(".node")
      .data(graph.nodes)
    .enter().append("circle")
      .attr("class", "node")
      .attr("r", 5)
      .style("fill", function(d) { return color(d.group); })
      .call(force.drag);
  node.append("title")
      .text(function(d) { return d.name; });
  force.on("tick", function() {
    link.attr("x1", function(d) { return d.source.x; })
        .attr("y1", function(d) { return d.source.y; })
        .attr("x2", function(d) { return d.target.x; })
        .attr("y2", function(d) { return d.target.y; });
    node.attr("cx", function(d) { return d.x; })
        .attr("cy", function(d) { return d.y; });
  });
});
</script>

Please find my [resume](/assets/pdfs/DeveshSeethiResume.pdf) and [CV](/assets/pdfs/DeveshSeethCV.pdf) for a detailed account of my skill-set and my projects.   

I have a go-getter personality, and I get things done. I enjoy getting engaged in challenging and open-ended problems to explore new paradigms of AI. I can quickly adapt to any environment and consume knowledge swiftly and build practical solutions. My flexibility in learning is a bi-product of my background in a mix of computer science and electronics. Additionally, my active research area involves leveraging AI algorithms to solve real-world problems in disease diagnostics and improve general public health, which is essentially multi-disciplinary research. I have experience in multi-disciplinary AI research with departments such as Chemistry and Behavioral and Aging Studies, where I seamlessly understood the problem,  identified, and probed critical AI-related aspects of the study. It is delightful to work in teams and I am also self-driven where my recipe for productivity is to generate critique, fine-tune/ debug methods, iterate and explore.   

My research so far has shown me the importance of AI in healthcare, which motivates me to improve the efficiency of existing deep learning models such as multimodal data such as vision, language, speech, and inertial sensors. I am also passionate about optimizing the algorithms and fine-tuning their performance to different hardware resources to make the solutions pervasive and bring a balance between accessibility and practicality.  


## Research Interests 

### PhD in Computer Science
Advisor : [Dr. Pratool Bharti](https://pratoolbharti.github.io/NIU/)     
My primary research includes leveraging AI to solve public health issues and build disease diagnostic models. I am currently working on building frameworks capable of detecting activity levels and behavioral patterns from cameras and subsequently using multimodal data from sensors and audio. My focus is mainly on computer vision and multimodal algorithms relating to panoptic segmentation, person re-identifaction, and point-of-interest tracking. The final outcome of the research is to build an effecient and optimized framework that healthcare facilities either small or large are able to leverage our proposed framework for extended periods with their hardware resources. In the last year, I worked on developing an AI solution for COVID-19 testing using explainable-AI techniques that give clinicians the ability to understand the biomarkers the . Thus reinforcing trust in our AI-model and providing a scope to dynamically understand the effects 
  

### Masters in Computer Science   
My research during masters included building machine learning and neural network models that uses sensor-fusion in several human activity recognition tasks. I also studied on differnt ways to optimize models using quantization and pruning for resource-constrained smartwatches. During the start of my master's program, I mainly worked on several projects relating to NLP with a focus on understanding the strategies and information dissiminated by bots in social media. 


### Bachelors in Electronics and Communication Engineering     
I worked on several projects relating to internet of things and embedded systems. I also interned at a defense research institution where I learned on how new embedded systems are tested and designed for integrating into systems at scale. I also got exposure to several professional organizations that are delineated in my Linkedin profile.   


### Hobbies  
[Running](https://www.strava.com/athletes/60983534) and reading [books](https://twitter.com/home).



