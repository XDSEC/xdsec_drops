# Drops for XDSEC: XDSEC\_Drops

This is a open-source article publish and share program. It's maintained by XDSEC and you may find a demo later, since the program is still under development.

## First-run

* First, you are required to install packages in `requirements.txt`
* Then you need install MongoDB and config it. We're using MongoDB currently to save articles you published, links you've submitted, snapshots of those links, and some other configurements. You should always be sure that you have configured it correctly in case of some diseasters.
* You are required to decide whether you want to run it through a front-end proxy, or make it run directly. This could be easily configured in the config file, and the fastest way is to boot it up directly. 
* Decide the method to save static files of the web cache. Currently, following methods are acceptable: Cloudinary or save it by yourself. You'd better read our document if you want to customize it, or you can use the default settings and create a folder which is writeable. 



Example configrue file:
net.listen.address=127.0.0.1
net.listen.port=8000
db.mode=mongodb
db.host=mongodb://127.0.1.1:3389
snapshot.power=on									# open snapshot for shared articles
snapshot.save.provider=local
snapshot.local.dir=static
snapshot.save.whitelist=*.png;*.jpg;*.gif;*.js;		# always download those files
snapshot.save.blacklist=*.iso;*.rar;*.zip;*.tar*;	# never download those files
snapshot.save.maxsize=1M							# download files not over this size
snapshot.save.smartcache=on							# open smart cache for some files, see smartcache.config
manage.owner=rem:1q3e2w4r							# default password is 1q3e2w4r
