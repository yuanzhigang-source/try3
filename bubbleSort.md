# 1.冒泡排序

``` java
@Test
public void bubbleSort(){
    int[] arr={3,55,44,66,77,10,52,33,11};
    int count=0；//统计次数
        for(int i=0;i<arr.length-1;i++){
            //比较
            for(int j=0;j<arr.length-1-i;j++){
                if(arr[j]>arr[j-1]){
                    //change position
                    int temp=arr[j];
                    arr[j]=arr[j+1];
                    arr[j+1]=temp;
                }
                cout++;
            }
        }
   System.out.println(Arrays.toString(arr));
   System.out.println('比较了'+count +'次')
}
```



