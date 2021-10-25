# thread_pool
C++ thread pool, support lambda function, function, operator

# 如何使用
```
int main() {
    std::cout << "hello world" << std::endl;

    ::inf::frame::ThreadPool pool;
    pool.init(10);
    pool.start();

    std::function<int(int, int)> f = [](int a, int b) {return a + b;};
     
    auto task = pool.submit(f, 10, 10);
    auto task2 = pool.submit(f, 20, 30);

    std::cout << task.get() << std::endl;
    std::cout << task2.get() << std::endl;


    sleep(10);
    pool.stop();
    return 0;

}
```
