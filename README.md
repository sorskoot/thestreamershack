# Notes

- do a [product search](https://affiliate-program.amazon.com/home/productlinks/search)

- we need the following info:
  
  - name: `document.querySelector('#ac-productlinks-preview-panel-text > a').innerText.split('-')[0].trim()`
  - description: `document.querySelector('#ac-productlinks-preview-panel-text > a').innerText.split('-').slice(1).join('-').trim()`
  - link: `document.querySelector('.ac-ad-code-short').value`
  - image: `document.querySelector('#ac-productlinks-preview-panel-image > a > img').getAttribute('src')`
  - tracking: `document.querySelector('#ac-productlinks-preview-panel-image > img').getAttribute('src')`

## steps to get data

1) click the 3 tabs to load all data
2) execute:
function getData(){
    let x = {
    name: document.querySelector('#ac-productlinks-preview-panel-text > a').innerText.split('-')[0].trim(),
description: document.querySelector('#ac-productlinks-preview-panel-text > a').innerText.split('-').slice(1).join('-').trim(),
link: document.querySelector('.ac-ad-code-short').value,
image: document.querySelector('#ac-productlinks-preview-panel-image > a > img').getAttribute('src'),
tracking: document.querySelector('#ac-productlinks-preview-panel-image > img').getAttribute('src')
    }
    return `- name: ${x.name}\n  description: ${x.description}\n  link: ${x.link}\n  image: ${x.image}\n  tracking: ${x.tracking}\n  category:\n`;
}

4) copy to Yaml