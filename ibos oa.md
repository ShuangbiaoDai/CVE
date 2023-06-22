SQL injection vulnerability exists in ibos OA v4.5.5


official website:http://www.ibos.com.cn/

verison:4.5.5

route:r=dashboard/roleadmin/edit&op=member

Present injection parameter:id

1.Function point: Background management = "Address book management =" foreground management permission = "Member management =" Add user function

![WPS图片(1)](https://github.com/ShuangbiaoDai/CVE/assets/47785707/e1734ea4-323f-4a8c-817f-2338531c1593)

The user name was successfully popped by reporting an error injection

![WPS图片(2)](https://github.com/ShuangbiaoDai/CVE/assets/47785707/5e3dd95c-6914-40b1-b06f-1a3ac18a2d79)

2.Follow up on the actionEdit() method by calling actionEdit() under the parent class through the ActionEdit () method

![WPS图片(3)](https://github.com/ShuangbiaoDai/CVE/assets/47785707/c8955158-a0b5-48bb-b844-f1e1ec0de07d)

The actionEdit() method in the parent class calls the fetchAllByRoleId() method under module to follow up on the method

![WPS图片(4)](https://github.com/ShuangbiaoDai/CVE/assets/47785707/6acee337-36ea-444d-8f5b-ccf2b8be903a)

Finally, the SQL statement is executed at findAll()

![WPS图片(5)](https://github.com/ShuangbiaoDai/CVE/assets/47785707/9413d860-3cd9-40fd-ac48-3f29b395deac)
