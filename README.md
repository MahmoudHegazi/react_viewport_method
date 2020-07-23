# react_viewport_method
How to add class to the element in the viewport and how to remove it 


```javascript
document.addEventListener('scroll', myFunction);
function myFunction() {
  var allElements = document.querySelectorAll('.help');
  var elmIndex = 1;
  for (var i=0; i < allElements.length; i++) {
    elmIndex = 1;
    let myrect = allElements[i].getBoundingClientRect();
    let elmlngt = allElements[i].clientHeight;
    elmlngt = -parseInt(elmlngt);
    if (myrect.top > elmlngt + 8 && myrect.top <= 8) {
      allElements[i].classList.add('green');
      elmIndex += i;
      console.log("elm" + elmIndex + "inviewport");
    } else {
      allElements[i].classList.remove('green');
      console.log("Class Removed From elm " + (i + 1));
    }
    
  }
  
  
}
```

طول ما react.top 
= 0 (اول المكان اللي بادي منه الحدث بيختلف بحاجة زي margin)
او اصغر من - طول العنصر السالب يبقي العنصر ده 
جوه viewport

