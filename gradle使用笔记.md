## gradle使用笔记

### 更改仓库地址

一个简单的办法，修改项目根目录下的build.gradle，将jcenter()或者mavenCentral()替换掉即可：

	allprojects { 
		repositories { 
			maven{ url 'http://maven.oschina.net/content/groups/public/'} 
		} 
	}

在 USER_HOME/.gradle/ 下面创建新文件 init.gradle，输入下面的内容并保存。

	allprojects{
	    repositories {
	        def REPOSITORY_URL = 'http://maven.aliyun.com/nexus/content/groups/public/'
	        all { ArtifactRepository repo ->
	            if(repo instanceof MavenArtifactRepository){
	                def url = repo.url.toString()
	                if (url.startsWith('https://repo1.maven.org/maven2') || url.startsWith('https://jcenter.bintray.com/')) {
	                    project.logger.lifecycle "Repository ${repo.url} replaced by $REPOSITORY_URL."
	                    remove repo
	                }
	            }
	        }
	        maven {
	            url REPOSITORY_URL
	        }
	    }
	}