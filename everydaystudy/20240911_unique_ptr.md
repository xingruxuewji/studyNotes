# 20240911 unique_ptr
unique_ptr是独占指针,对于一个对象,只能有一个独占指针指向它。shared_ptr则允许多个指针指向同一个对象。

unique_ptr不允许拷贝与赋值，可以使用移动语义move。它与auto_ptr的区别有它允许函数返回unique_ptr,并且允许在容器中使用(通过移动语义move);

unique_ptr初始化
```cpp
unique_ptr<int> uniPtr(new int(5));
```

函数返回unique_ptr
```cpp
unique_ptr<double> funCopy(double num){
    unique_ptr<double> tmpPtr(new double(num));
    return tmpPtr;
}
```

容器使用unique_ptr
```cpp
std::vector<unique_ptr<int>> vec；
vec.push_back(std::move(1));
```

<br>unique_ptr可以指定删除器,删除器可以先指定

```cpp
//在deleteFunP中写删除操作
void(*deleteFunP)(int, int);

unique_ptr<int, deleteFunP> numP(new(5));

```






