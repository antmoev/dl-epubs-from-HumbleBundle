#WIP :bug:

I had to tinkle on this one to make it work for HB... 

This is raw download. It do no check if some are already downloaded.

```js

//Copy-paste in your web browser console at https://www.humblebundle.com/home/library

const arrBooks = $('div.text-holder').children('h2')
arrBooks.each((index, book)=>{
    
    setTimeout((idx, el)=>{
        console.log(`Downloading ${idx}th : ${$(el).html()}`)
        $(el).click();
        const epub = $('h4:contains(EPUB)') 
        if (epub.length) {
        epub.click();
        } else {
          console.log(`WARNING: No EPUB format for ${$(arrBooks[idx]).html()}`) 
          $('h4')[0].click() 
        }
    },
    index*4000, //4 sec delay
    index, book);  //args
})
```

Based on the work of : [bulk dl](https://liliputing.com/how-to-bulk-download-humble-bundle-ebook-purchases/)
