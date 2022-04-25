---
title: Throughput and Latency
date: 2022-05-09
image: /assets/images/2021/coolimage.jpg
---

Currently working on this post!

Throught put in simplest terms means the number of data samples processed in a given time. We are concerened about throughput when we want to process large amount of data in a given period of time. One can maximize throughput by processing batches of input data and equip the resources exhaustively to maximize data processed per unit time. For example, during testing, if the dataset has a large number of data samples, a high throughput becomes favorable to save time.

On the other hand, latency is the time taken to process a single sample. In real-world inference cases, the latency of the model is increasingly important for providing rapid inference rates with minimum delays. For example, if a phone camera uses object detection, the time taken to process each image should be minimized to make the application more acceptable to the end user. 

Overall, latency is measured when processing one sample and throughput in large batches, typically of size 128-256. It comes at no surprise that the inference times are much dependant on the data, model, and the hardware device. 

Hardware description : CPU | GPU | FPGA

Upload benchmark results of object detection for inception, resnet models for different precisions and batch sizes

How to benchmark inference models : 

```python
for model_name in model_names_:
    for precision in precisions:        
        for batch_size in batch_sizes:
            model_local_path = get_model_local_path('resnet101' + '_')
            start = time.time()
            #enable logging
            %run models/benchmarks/launch_benchmark.py \
                --in-graph $get_model_local_path(model_name + "_")\
                --model-name model_name\
                --framework tensorflow \
                --precision $precision \
                --mode inference \
                --batch-size=batch_size\
                --socket-id 0
                end = time.time() - start
                # To be implemented
                # subtract end time with total inference time to get the initialization time
```

# Write about both during training and inference
    
<!-- 
This is your first blog post. And it can contain a lot of stuff. So let's go through a few things.

## Code for fun or profit

Having good looking (totally opiniated here, no) code snippets is mandatory. At least for myself. The included Prism config is based on [this selection](https://prismjs.com/download.html#themes=prism-coy&languages=markup+css+clike+javascript+bash+docker+java+regex+ruby+rust+scala+shell-session+typescript&plugins=show-language+toolbar). No standard theme has been chosen, there are some modifications to fit the Chirpy UX.

Find here an excerpt of the visuals.

### Bash

```bash
if [ -z "$HEROKU_PWA_APP_NAME" ]; then
    echo "Please provide HEROKU_PWA_APP_NAME environment variable"
    exit 1
fi
```

### JavaScript

```javascript
const jestLwcConfig = require("@lwc/jest-preset");
import { resolve } from "path";

export const jestConfig = {
    ...jestLwcConfig,
    resolver: resolve(__dirname, "../utils/resolver.js")
};
```

## Images, images, images

First, you'll notice this stunning picture. I got it royalty-free from Pixabay (great site). Now, that's not the point that I want to make here. The image is not added via Markdown, but instead via the `image` value of the Markdown front matter. As it's always good IMHO to start with a visual you'll get a standardized way of addding an image asset.

Second, the image is optimized for your browser size _and_ browser. Depending on what you currently use as browser you'll get i. e. a JPG or a WebP file. All in the right size for the screen. Obviously, all images have standard settings for lazy loading etc.

## Headings all over the place

It's all standard markdown to render the headings, and as well to display the table of contents (TOC) on the right side.

Note: never ever add a first level heading (aka: `h1`) to your page. This will break accessibility, as the title is already an h1, and will be represented as such in the rendered HTML.

## Other stuff

As to be expected you can do all the things that are _standard_ Markdown. So tables, blockquotes etc. And if you prefer to add custom Markdown functionality, just extend the configuration with custom [markdown-it](https://github.com/markdown-it/markdown-it) plugins. -->
