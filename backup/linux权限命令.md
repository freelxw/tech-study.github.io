在Linux操作系统中，设置文件和目录权限的命令主要有以下几种：`chmod`、`chown`、`chgrp`。这些命令可以用来修改文件和目录的权限、所有者和所属组。以下是详细介绍和使用示例。

### 1. `chmod` 命令

`chmod` 命令用于改变文件或目录的权限。

#### 权限表示

- **r**：读权限（Read），数值表示为4
- **w**：写权限（Write），数值表示为2
- **x**：执行权限（Execute），数值表示为1

权限可以用符号表示（rwx）或数值表示（0-7）。

#### 使用方式

**符号模式**：
```bash
chmod [选项] 模式 文件
```

**数字模式**：
```bash
chmod [选项] 数字模式 文件
```

#### 示例

**符号模式**：
```bash
chmod u+rwx,g+rx,o+r myfile  # 给文件myfile的所有者(u)读、写、执行权限，组用户(g)读、执行权限，其他用户(o)读权限
chmod a+r myfile            # 给所有用户(a)读权限
chmod u-w myfile            # 去掉所有者的写权限
```

**数字模式**：
```bash
chmod 755 myfile            # 设置文件myfile的权限为所有者读、写、执行，组用户和其他用户读、执行
chmod 644 myfile            # 设置文件myfile的权限为所有者读、写，组用户和其他用户读
```

### 2. `chown` 命令

`chown` 命令用于改变文件或目录的所有者和所属组。

#### 使用方式

```bash
chown [选项] 用户[:组] 文件
```

#### 示例

```bash
chown root myfile            # 将文件myfile的所有者改为root
chown root:admin myfile      # 将文件myfile的所有者改为root，所属组改为admin
chown :admin myfile          # 将文件myfile的所属组改为admin，所有者不变
chown -R root:admin mydir    # 递归改变目录mydir及其内容的所有者为root，所属组为admin
```

### 3. `chgrp` 命令

`chgrp` 命令用于改变文件或目录的所属组。

#### 使用方式

```bash
chgrp [选项] 组 文件
```

#### 示例

```bash
chgrp admin myfile           # 将文件myfile的所属组改为admin
chgrp -R admin mydir         # 递归改变目录mydir及其内容的所属组为admin
```

### 4. `umask` 命令

`umask` 命令用于设置默认权限掩码，以确定新创建文件和目录的默认权限。

#### 使用方式

```bash
umask [权限掩码]
```

#### 示例

```bash
umask 022                    # 设置默认权限掩码为022，新建文件默认权限为755（777-022），新建目录默认权限为644（666-022）
umask                        # 查看当前权限掩码
```

### 5. 示例综合应用

**创建文件和目录并设置权限**：
```bash
touch myfile
mkdir mydir
chmod 755 myfile
chmod 700 mydir
chown user1:group1 myfile
chown user1:group1 mydir
```

**查看文件权限**：
```bash
ls -l myfile mydir
```

输出示例：
```
-rwxr-xr-x 1 user1 group1 0 May 24 10:00 myfile
drwx------ 2 user1 group1 4096 May 24 10:00 mydir
```

以上命令展示了如何使用 `chmod`、`chown` 和 `chgrp` 命令设置文件和目录的权限、所有者和所属组。在实际操作中，灵活使用这些命令可以有效管理Linux系统中的文件和目录权限，确保系统安全和资源访问的合理性。