# algorithms

###Bubble Sort
```javascript
function bubbleSort(a){
	for(var i=a.length;i>0;i--){
		for(var j=0;j<i-1;j++){
			if(a[j]>a[j+1]){
				//swap
				var t=a[j];a[j]=a[j+1];a[j+1]=t;
			}
		}			
	}
}
```

