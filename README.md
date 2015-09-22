# Algorithms

###Bubble Sort
```javascript
function bubbleSort(a){
	for(var i=a.length;i>0;i--){
		for(var j=0;j<i-1;j++){
			if(a[j]>a[j+1]){
				var t=a[j];a[j]=a[j+1];a[j+1]=t;//swap
			}
		}			
	}
}
```

###Selection Sort
```javascript
function selectionSort(a){
	for(var i=0;i<a.length-1;i++){
		var minPosition=i;		
		for(var j=i;j<a.length;j++){
			if(a[j]<a[minPosition]){				
				minPosition=j;
			}
		}		
		var t=a[i];a[i]=a[minPosition];a[minPosition]=t;//swap
	}
}
```

