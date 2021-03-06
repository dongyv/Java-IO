# Java-IO
Java网络编程：BIO、NIO、AIO
anxpp.com

---
## 一、IO请求的两个阶段：
- 等待资源阶段：IO请求一般需要请求特殊的资源（如磁盘、RAM、文件），当资源被上一个使用者使用没有被释放时，IO请求就会被阻塞，直到能够使用这个资源。
- 使用资源阶段：真正进行数据接收和发生。

## 二、在等待数据阶段，IO分为阻塞IO和非阻塞IO。
- 阻塞IO： 资源不可用时，IO请求一直阻塞，直到反馈结果（有数据或超时）。
- 非阻塞IO：资源不可用时，IO请求离开返回，返回数据标识资源不可用

## 三、在使用资源阶段，IO分为同步IO和异步IO。
- 同步IO：应用阻塞在发送或接收数据的状态，直到数据成功传输或返回失败。
- 异步IO：应用发送或接收数据后立刻返回，数据写入OS缓存，由OS完成数据发送或接收，并返回成功或失败的信息给应用。

## 四、IOPS，即每秒钟处理的IO请求数量。
- IOPS是随机访问类型业务（OLTP类）很重要的一个参考指标。

---
# NIO
NIO主要有三大核心部分：Channel(通道)，Buffer(缓冲区), Selector。<br>
传统IO基于字节流和字符流进行操作，而NIO基于Channel和Buffer(缓冲区)进行操作，数据总是从通道读取到缓冲区中，或者从缓冲区写入到通道中。<br>
Selector(选择区)用于监听多个通道的事件（比如：连接打开，数据到达）。因此，单个线程可以监听多个数据通道。
