# ImmortalWRT for Intel G7505
+ 网卡驱动
    + 有线网卡：只支持 I225/I226
    + 无线网卡：不支持
+ 开启串口调试，波特率为 `115200`
+ 性能优化
    + 开启 LTO
    + 使用 Ofast 优化
    + 目标架构提升到 `tigerlake` (11 代 intel，支持 AVX512)
    + golang：目标架构提升到 X86_64-V4
    + Rust：使用 O3 优化，目标架构提升到 `tigerlake` (11 代 intel，支持 AVX512)
+ root 分区大小为 1024MB
+ kernel 分区大小为 32MB
+ 使用 nginx 替换 uhttp
    + 管理页面默认不使用 https（使用 nginx 后会默认启用 https）
