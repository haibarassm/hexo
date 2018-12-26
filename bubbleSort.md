# 冒泡排序
## 基本思想
设数组的长度为N：   
（1）比较前后相邻的二个数据，如果前面数据大于后面的数据，就将这二个数据交换。  
（2）这样对数组的第0个数据到N-1个数据进行一次遍历后，最大的一个数据就“沉”到数组第N-1个位置。  
（3）N=N-1，如果N不为0就重复前面二步，否则排序完成。  
## 实现方式
### 第一种实现
```
/**
 * 冒泡排序的第一种实现, 没有任何优化
 * @param a
 * @param n
 */
public static void bubbleSort1(int [] a, int n){
    int i, j;

    for(i=0; i<n; i++){//表示n次排序过程。
        for(j=1; j<n-i; j++){
            if(a[j-1] > a[j]){//前面的数字大于后面的数字就交换
                //交换a[j-1]和a[j]
                int temp;
                temp = a[j-1];
                a[j-1] = a[j];
                a[j]=temp;
            }
        }
    }
}
```
### 第二种方式
```
/**
 * 设置一个标志，如果这一趟发生了交换，则为true，否则为false。明显如果有一趟没有发生交换，说明排序已经完成。
 * @param a
 * @param n
 */
public static void bubbleSort2(int [] a, int n){
    int j, k = n;
    boolean flag = true;//发生了交换就为true, 没发生就为false，第一次判断时必须标志位true。
    while (flag){
        flag=false;//每次开始排序前，都设置flag为未排序过
        for(j=1; j<k; j++){
            if(a[j-1] > a[j]){//前面的数字大于后面的数字就交换
                //交换a[j-1]和a[j]
                int temp;
                temp = a[j-1];
                a[j-1] = a[j];
                a[j]=temp;

                //表示交换过数据;
                flag = true;
            }
        }
        k--;//减小一次排序的尾边界
    }//end while
}
```
### 第三种
```
public static void bubbleSort3(int [] a, int n){
    int j , k;
    int flag = n ;//flag来记录最后交换的位置，也就是排序的尾边界

    while (flag > 0){//排序未结束标志
        k = flag; //k 来记录遍历的尾边界
        flag = 0;

        for(j=1; j<k; j++){
            if(a[j-1] > a[j]){//前面的数字大于后面的数字就交换
                //交换a[j-1]和a[j]
                int temp;
                temp = a[j-1];
                a[j-1] = a[j];
                a[j]=temp;

                //表示交换过数据;
                flag = j;//记录最新的尾边界.
            }
        }
    }
}
```