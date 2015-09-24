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

###Insertion Sort
```javascript
function insersionSort(a){
	for(var i=0;i<a.length;i++){
		var currentValue = a[i];
		var position = i;
		while(position>0 && a[position-1]>currentValue){
			a[position]=a[position-1];
			position--;
		}
		a[position]=currentValue;
	}
}
```


###Merge Sort
```javascript
function mergeSort(a){
	if(a.length > 1){
		var mid = Math.floor(a.length/2);
		var left = a.slice(0,mid); 
		var right = a.slice(mid,a.length);
		mergeSort(left);mergeSort(right);
		//merging sorted arrays
		var i=j=k=0;
		while(i<left.length && j< right.length){			
			left[i]<right[j] ? a[k++]=left[i++] : a[k++]=right[j++];
		}
		while(i < left.length){
			a[k++]=left[i++];
		}		
		while(j < right.length){
			a[k++]=right[j++];
		}
	}
}
```


###Quick Sort
```javascript
function partition(a,left,right){
	var i = left, j = right, tmp, pivot = a[left];	
	while( i <= j){
		while(a[i]<pivot) i++;
		while(a[j]>pivot) j--;
		if(i<=j){
			tmp = a[i];	a[i]=a[j]; a[j]=tmp;//swap
			i++; j--;
		}	
	}	
	return i;
}

function quickSort(a,left,right){
	var index = partition(a,left,right);
	if(left < index-1) quickSort(a,left,index-1);		
	if(index < right) quickSort(a,index,right);
}

quickSort(a,0,a.length-1);
```


