# KSpeeder 测速文件

三个 ZIP 文件用于下载测速，大小指 ZIP 文件本身，单位为 MiB，1 MiB = 1,048,576 字节。

| 文件 | 大小 | 字节数 |
| --- | ---: | ---: |
| `2M.zip` | 2 MiB | 2,097,152 |
| `60M.zip` | 60 MiB | 62,914,560 |
| `160M.zip` | 160 MiB | 167,772,160 |
| `sample.txt` | 短文本 | 78 |

每个 ZIP 包含一个 `payload.bin`，使用 DEFLATE 压缩确定性的伪随机数据，避免高度重复内容被压缩成很小的文件。ZIP 注释填充用于使归档总大小精确匹配目标。文本文件只包含无意义的公开内容。

ZIP 文件由 Git LFS 管理，文本文件和 SHA256SUMS 直接保存在 Git 中。GitHub 普通 Git 文件上限为 100 MiB，参见 [GitHub 文件大小限制](https://docs.github.com/en/repositories/working-with-files/managing-large-files/about-large-files-on-github)。

安装 Git LFS 后获取完整文件：

```sh
git lfs install
git clone https://github.com/kspeeder/speed-test.git
cd speed-test
git lfs pull
sha256sum -c SHA256SUMS
```

后续配置测速 URL 时必须确认收到 ZIP 实际数据，而不是 Git LFS 指针文本。本次仅准备并提交文件，没有修改 KSpeeder 测速配置。
