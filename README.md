# Notes

- do a [product search](https://affiliate-program.amazon.com/home/productlinks/search)

- we need the following info:
  
  - name: `document.querySelector('#ac-productlinks-preview-panel-text > a').innerText.split('-')[0].trim()`
  - description: `document.querySelector('#ac-productlinks-preview-panel-text > a').innerText.split('-').slice(1).join('-').trim()`
  - link: `document.querySelector('.ac-ad-code-short').value`
  - image: `document.querySelector('#ac-productlinks-preview-panel-image > a > img').getAttribute('src')`
  - tracking: `document.querySelector('#ac-productlinks-preview-panel-image > img').getAttribute('src')`

## steps to get data

1) run this on the product page:
function getData(){
    return {
    name: document.querySelector('#ac-productlinks-preview-panel-text > a').innerText.split('-')[0].trim(),
description: document.querySelector('#ac-productlinks-preview-panel-text > a').innerText.split('-').slice(1).join('-').trim(),
link: document.querySelector('.ac-ad-code-short').value,
image: document.querySelector('#ac-productlinks-preview-panel-image > a > img').getAttribute('src'),
tracking: document.querySelector('#ac-productlinks-preview-panel-image > img').getAttribute('src')
    }
}

JSON.stringify(getData())

2) past in Notepad ++
3) Format, remove quotes and comma at the end of the line
4) copy to Yaml