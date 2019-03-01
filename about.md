---
layout: page
title: "About"
description: "关于生活 " 
header-img: "img/green.jpg"
---

我是夏红彬，旅游规划实习生，品牌LOGO设计师。

2016年由世界著名设计学院，德国[包豪斯](https://dwz.cn/AXyo8pVi)学院，景观园林硕士研究生王瑞珏老师启蒙，从此走上设计之路。在此后的两年时间持续接受王老师的指导并跟随老师的脚步进行学习。期间曾作为成都职业技术学院景区开发与管理专业，设计代表团队成员，参加2018全国高校数字艺术大赛，在这场比赛中作品获得空间设计一等奖。同年团队作品《城市道路空间设计》获得德国DLA空间环境入围奖（中国高校唯一获奖团队）2018年至今在四川师范大学旅游设计研究规划院刘旺教授的旗下从事旅游规划实习生的工作，目前在品牌LOGO设计方面也有所研究，爱好是帮助创业团队开启品牌设计第一步。

## 回未视戒

博客叫回未视戒，回味世界。关于设计，关于生活，关于旅游。

本人学历尚浅，文章中有不实和不当之处，还请批评斧正。

## 回未信条

重要的不是结果而是思考和过程。

在开始一件事情前我喜欢充分的沟通，没有沟通何来成长？

## 工作方向

带着做品牌的要求去做LOGO，而不仅仅是做一个图形设计师。

## 图形作品

**[点我](https://huiweishijie.com/milestone/)**
我的作品和我正在做的工作


## 最近在干嘛？

- 2019-02网站的优化;
- 2019-02毕业设计的思考;


## 坚信

- *学习的态度：保持好奇心;
- *做人的原则：己所不欲勿施于人;
- *设计的风格：适合的才是最好的;
- *心态平和、不急不躁、身形挺直、自信真诚、与人和善;*

## 联系

邮箱：xiahibb@gmail.com


## changelog

- 2019-2-17修复DNS
- 2019-2-16基础信息

<?php
	//首先你要有读写文件的权限，首次访问肯不显示，正常情况刷新即可
	$online_log = "slzxrs.dat"; //保存人数的文件到根目录,
	$timeout = 30;//30秒内没动作者,认为掉线
	$entries = file($online_log);
	$temp = array();
	for ($i=0;$i<count($entries);$i++){
		$entry = explode(",",trim($entries[$i]));
		if(($entry[0] != getenv('REMOTE_ADDR')) && ($entry[1] > time())) {
			array_push($temp,$entry[0].",".$entry[1]."\n"); //取出其他浏览者的信息,并去掉超时者,保存进$temp
		}
	}
	array_push($temp,getenv('REMOTE_ADDR').",".(time() + ($timeout))."\n"); //更新浏览者的时间
	$slzxrs = count($temp); //计算在线人数
	$entries = implode("",$temp);
	//写入文件
	$fp = fopen($online_log,"w");
	flock($fp,LOCK_EX); //flock() 不能在NFS以及其他的一些网络文件系统中正常工作
	fputs($fp,$entries);
	flock($fp,LOCK_UN);
	fclose($fp);
	echo "在线人数：".$slzxrs."人";
?>







