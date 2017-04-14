# 创建一个翻译-Creating a translation

If you would like to have Flowblade translated into your language you can help by contributing a translation of Flowblade in your language.（如果你想把流刀翻译成你用的语言，可以贡献出用你的语言翻译的流刀软件。）

Flowblade uses the standard [GNU "gettext" utilities](http://www.gnu.org/software/gettext/manual/gettext.html) to translate the application. GNU "gettext" is a relatively complex tool, but **Flowblade provides a set of scripts that make it easier to create translations** without using "gettext" directly.（流刀使用标准的GNU"gettext“事业来翻译应用，GNU"gettext”是一个相当复杂的工具，但是**流刀提供一系列脚本使创建翻译工作更简单** 不用直接使用“gettext”）

### 大概步骤-Steps Overview
1. Use **git** to pull repository version of Flowblade（使用 **git** 拉下流刀的版本仓库）
2. Use the provided scripts to create a translation template for your language（使用提供的脚本来为你的语言创建一个翻译模板）
3. Edit the created template to create the translation and compile **.mo** file from it to see your work（编辑创建好的模板来创建翻译，从中编译 **.mo** 文件来查看你的工作）
4. Send the created **.po** file to project lead（发送这个创建好的 **.po** 文件给项目负责人）

### 1. Use **git** to pull repository version of Flowblade（使用 **git** 拉下流刀的版本仓库）

To create a translation you should probably first install the repository version of Flowblade using **git** so that you can edit and compile the translation file ``Flowblade.po``, see [安装指导-Install Instructions](https://github.com/jliljebl/flowblade/blob/master/flowblade-trunk/docs/INSTALLING.md).
为了创建一个翻译，首先你应该使用 **git** 安装流刀的版本仓库,才能编辑和编译 ``Flowblade.po`` 这个翻译文件，查看[安装向导](https://github.com/wzba/flowblade/blob/master/flowblade-trunk/docs/INSTALLING.md).

### 2. Use the provided scripts to create a translation template for your language(使用提供的脚本来为你要翻译的语言创建一个翻译模板)

  * Open Flowblade and select *Help -> Runtime Environment* from menu to see the *two letter locale code* for your OS install. For example *fr* for French, *fi* for Finnish etc. Information is under the header *General*.(打开Flowblade，然后从menu选择 *Help -> Runtime Environment* 为你安装系统查看*two letter locale code* )
  * Open terminal in folder ``.../flowblade-trunk/Flowblade/locale`` that can be found in the folder you installed repository version of Flowblade in.(在 ``.../flowblade-trunk/Flowblade/locale`` 目录，这个目录可以在你安装流刀版本库的目录找到)
  * To create a new translation give a command in the terminal(在终端里用下面命令行来创建一个翻译):
```bash
./add_language LANGUAGE_CODE
```
 in which LANGUAGE_CODE is the two letter language code for your locale.(这个LANGUAGE_CODE就是你本地语言的两个语言代码信件)
  
### 3. Edit the created template to create the translation and compile **.mo** file from it to see your work(编辑创建的模板来创建翻译然后编译） ###

  * A folder named with the LANGUAGE_CODE for your language can be found in the ``/locale`` folder(在 ``/locale``目录能为你的翻译语言找到一个名为LANGUAGE_CODE的目录)
  * Inside that folder is a ``/LC_MESSAGES`` folder in which there is a file called ``Flowblade.po``. This is the file used to create the translation.(在这个目录是一个 ``/LC_MESSAGES`` 目录，它下面有一个文件叫 ``Flowblade.po`` .这个文件就是用来创建翻译用的。)
  * Open the file ``Flowblade.po`` in a text editor. Translations are given by writing the the translations inside quotes on lines staring with text ``msgstr``. To traslate the menu item *Open...* you would need to fill the ``msgstr`` in example below(用一个编辑器打开 ``Flowblade.po`` ，需要翻译的内容已经通过引号给出来了，只需要找到前面是 ``msgstr`` 的一对引号，翻译上一行中的内容到这个引号中即可。翻译菜单栏的 ``Open`` 你需要在 ``msgstr`` 项里填上翻译的内容，就像下面的例子那样):
```bash
#: useraction.py:489
msgid "Open.."
msgstr ""
```
  * To see the translations in the application, you need to compile them into a machine readable *.mo* file. Go to ``/locale`` folder and give command(为了能在应用程序中看到翻译的成果，你需要将它们编译成机器能读懂的 *.mo* 文件。切换到 ``/locale``目录，然后运行下列命令):
```bash
./compile_language LANGUAGE_CODE
```
  * Launch repository version of Flowblade to view your translations.(启动流刀的版本库来查看你的翻译成果)



### 4. Contributing a translation
Send the created ``Flowblade.po`` file to janne.liljeblad@gmail.com or submit a Github pull request. Please mention words Flowblade, translation and the LANGUAGE_CODE in the subject line. Translation will be in the next release.


## Updating translation ##
If a translation already exists and you want to update it:

 * Go to the */locale* folder and give command:
```bash
./update_language LANGUAGE_CODE
```
 * Translate application as described above.
