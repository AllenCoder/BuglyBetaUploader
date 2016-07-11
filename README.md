# Beta Gradle���ʹ��˵��



�ڸ�Ŀ¼�µ�build.gralde�ļ���depandencies��buildscript���֣�����ӣ�

```
 dependencies {
        classpath 'com.tencent.bugly.plugin:betauploader:latest.release'
    }
```

����latest.releaseΪ������°棬����ָ������汾��ָ����1.0.0��
��module��build.gradle�ļ��Ķ�����ӣ�
```
apply plugin: 'com.tencent.bugly.plugin.betauploader'

beta {
    appId = '<App ID>'
    appKey = '<App Key>'
}
```
����appId��appKey֮�⣬�����������������ԣ������б����£�

| ���� | ֵ  | ˵�� |
| --- | --- | --- |
|appId |String| App ID <��ѡ>|
| appKey |String| App Key <��ѡ>|
| expId| String | ����汾id��Ĭ��Ϊ�� |
| title | String | �汾���ƣ�Ĭ����`<projectname>-<version name><version code> `����|
| desc | String | �汾������Ĭ��Ϊ�� |
| secret | int | ������Χ��1�������ˣ�2�����룬4����Ա��5QQȺ��6��������Ĭ�Ϲ��������ˣ�|
| users | String | ���������Χ��"QQȺ"��QQȺ�ţ����������Χ��"������"��QQ���룬��ʹ��;�зֿ���5000�����ڡ�����������������|
| password | String | ����(���������Χ��"����"������)| 
| download_limit | int |��������(����0��Ĭ��1000)|
| apkFile| String | ָ���ϴ���apk�ļ����粻ָ�����ϴ�������apk·��|
| enable | Boolean | ������أ�Ĭ��Ϊtrue|
| autoUpload | Boolean | �Ƿ��Զ��ϴ���Ĭ��Ϊfalse |
| debugOn |Boolean | debugģʽ�Ƿ��ϴ��� Ĭ��Ϊfalse|



`<Project>/build.gradle`�ļ����£�
```
buildscript {
        repositories {
            jcenter()
        }
        dependencies {
            ...
            classpath 'com.tencent.bugly.plugin:betauploader:latest.release'
        }
    }}
```
���С�latest.release�����ò�����°汾�����²��ֻ��ҪRebuildһ�¹��̼��ɡ�

`<Project>/<Module>/build.gradle`�ļ����£�
```
apply plugin: 'betauploader'
    ...
    beta { 
        appId = '900000000'
        appKey = 'abcdefghijklmn'
    }
```

��ĿӦ����Beta���֮�󣬲��Ĭ���ǿ����ģ����ڹ���Gradle projects������������task��
![task | center](./images/1467976971701.png)



����ֱ�ӵ��ִ�л����������������������
```
gradle uploadReleaseBetaApkFile
```

�ϴ��ɹ�֮��Ϳ������ڲ�ƽ̨�����汾��Ϣ��
![Alt text](./images/1467977676237.png)















