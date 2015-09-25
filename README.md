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


###String Permutations
```javascript
function permute(prefix,str){
	var n = str.length;
	if(n==0){
		console.log(prefix);
	}else{
		for(var i=0;i<str.length;i++){
			permute(prefix+str.charAt(i),str.substring(0,i)+str.substring(i+1,n));		
		}
	}	
}
permute("","abc");
```
###Search in JSON
```javascript
function search(node, key){
	for(var name in node){
		var child= node[name];
		if(name===key){
			return child;
		}else if (typeof child === "object"){
			var t=search(child, key);
			if(t)return t;
		}		
	}
}
console.log(search({"a":{"b":{}},"c":{"d":{"e":{},"f":{"h":[{"i":{"l":"111","m":"222"},"j":{"n":"333"}},{"k":{}}]},"g":{}}}},  'h'));
```
###Towers of Hanoi
```javascript
//move n disks from A to B
function hanoi(n, A, B, C){
	if(n>0){		
		hanoi(n-1,A,C,B);//move n-1 disks from A to C 
		console.log('move disk:'+ n + ' from:'+A+"  to: "+B	);//move nth disk from A to B
		hanoi(n-1,C,B,A);//move n-1 disks from C to B 
	}	
}
hanoi(3,'A','B','C');
```
