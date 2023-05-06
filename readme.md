# Notifier

[![Go Report Card](https://goreportcard.com/badge/github.com/gozelle/notifier)](https://goreportcard.com/report/github.com/gozelle/notifier)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

一个简洁的、遵循日志打印习惯的消息通知库。

## 特性

* 简单
* 驱动抽象，实现一个方法即可对接，已对接钉钉；


## 安装

```go
go get github.com/gozelle/notifier 
```

## 快速上手

```go
package main

func main {
	robot := dingrobot.NewRobot(
		"https://oapi.dingtalk.com/robot/send?access_token=c8487958cbb991620877cbbe645e3ddd5c82cf0ab99681a8f70fae6c5e63d217",
		"SECa9d4d94de78b8b9afe45548dc25559c1a2ae00628a0b3ae372b05d9506c8af9e",
	)
	notify := notifier.NewNotify(robot)
	
	go func() {
		notify.Run()
	}()
	
	notify.Infof("日报生成成功")
	notify.Errorf("数据统计错误: %s", errors.New("invalid params"))
	
	select {}
}
```

## 许可证

该项目采用 MIT 许可证。详见 [LICENSE](./LICENSE) 文件。

## 鸣谢

- 感谢所有人。