# 修改魔兽字体文件的DOS批处理脚本  by 凌晨凉风-格瑞姆巴托
将此批处理脚本wowfont.bat放在魔兽字体目录(fonts)里;


#### 使用办法：

1 拖拉相应字体的文件到此脚本文件里;

2 运行此脚本然后在拖拉字体文件到运行窗口里;

#### 此脚本的行为：

1、将拖放到脚本的文件复制改名到脚本所在目录里对应字体文件名；

2、将脚本目录里对应的文件复制备份为 ...BAK.TTF；


#### 建立一个文本文档将下面代码复制黏贴，然后另存为*.bat到魔兽fonts目录里：保存类型选所有文件，编码选ANSI；
#### 代码: 
  
```
@echo off
CLS

color 0a
ECHO 此脚本的行为：
ECHO 1、将拖放到脚本的文件复制改名到脚本所在目录里对应字体文件名；
ECHO 2、将脚本目录里对应的文件复制备份为 ...BAK.TTF；
ECHO.
ECHO.By 凌晨凉风-格瑞姆巴托
set fp=%1
if not defined fp (GOTO fp)else (GOTO MENU)


:fp
ECHO.
ECHO 请将字体文件拖进来然后回车确定:
set /p fp=
goto MENU
PAUSE

:MENU
ECHO. 
ECHO.
ECHO.  =-=-=-=-=将选择字体改为以下字体=-=-=-=-=
ECHO.
ECHO.  1  战斗数字字体(ARKai_C.TTF)
ECHO.
ECHO.  2  默认字体(ARKai_T.TTF)
ECHO.
ECHO.  3  聊天字体(ARHei.TTF)
ECHO.
ECHO.  4  金币、堆叠、按键绑定等字体(FRIZQT__.TTF)
ECHO.
ECHO.  5  生命条、经验条上的字体(ARIALN.TTF)
ECHO.
ECHO.  6  任务说明和书信、石碑的正文字体(FZBWJW.TTF)
ECHO.
ECHO.  7  物品、技能的说明字体(FZXHJW.TTF)
ECHO.
ECHO.  8  *** 更换新字体 ***
ECHO.
ECHO.  0  退   出
ECHO.
ECHO.  =-=-=-=-=By 凌晨凉风-格瑞姆巴托=-=-=-=-=
ECHO.
ECHO.输入选择对应序号回车确定：
set /p  ID=
if "%id%"=="1" goto cmd1
if "%id%"=="2" goto cmd2
if "%id%"=="3" goto cmd3
if "%id%"=="4" goto cmd4
if "%id%"=="5" goto cmd5
if "%id%"=="6" goto cmd6
if "%id%"=="7" goto cmd7
if "%id%"=="8" goto cmd8
if "%id%"=="0" exit
PAUSE


:cmd1
copy "%~dp0ARKai_C.TTF" "%~dp0ARKai_Cbak.TTF"
copy %fp% "%~dp0ARKai_C.TTF"
GOTO MENU



:cmd2
copy "%~dp0ARKai_T.TTF" "%~dp0ARKai_Tbak.TTF"
copy %fp% "%~dp0ARKai_T.TTF"
GOTO MENU


:cmd3
copy "%~dp0ARHei.TTF" "%~dp0ARHeibak.TTF"
copy %fp% "%~dp0ARHei.TTF"
GOTO MENU

:cmd4
copy "%~dp0FRIZQT__.TTF" "%~dp0FRIZQT__bak.TTF"
copy %fp% "%~dp0FRIZQT__.TTF"
GOTO MENU

:cmd5
copy "%~dp0ARIALN.TTF" "%~dp0ARIALNbak.TTF"
copy %fp% "%~dp0ARIALN.TTF"
GOTO MENU

:cmd6
copy "%~dp0FZBWJW.TTF" "%~dp0FZBWJWbak.TTF"
copy %fp% "%~dp0FZBWJW.TTF"
GOTO MENU

:cmd7
copy "%~dp0FZXHJW.TTF" "%~dp0FZXHJWbak.TTF"
copy %fp% "%~dp0FZXHJW.TTF"
GOTO MENU

:cmd8
goto fp
```  


