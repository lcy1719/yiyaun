> **代码提供有偿远程调试，29包启动成功！不管你有没有运行环境，哪怕你是刚买的新电脑，也包启动运行成功！提供有偿讲解，有不懂的地方随便问！问到会为止！**
## 源码获取（4.9元包含代码+数据库+有的送报告文档具体扫码询问，代码截图在下面）：
![微信图片_20241218164848](https://github.com/user-attachments/assets/646b2784-afb8-47ee-a4d4-5ccc9f96b331)
## 系统介绍
**基于SpringBoot+Vue实现的医院管理系统采用前后端分离架构方式，系统设计了管理员、医生、病人三种角色，系统实现了用户登录与注册、医生信息管理、患者信息管理、挂号信息管理、药物信息管理、检查项目管理、病床信息管理、排班信息管理、数据统计分析等功能。**
## 技术选型
开发工具：idea2020.3+Webstorm2020.3
运行环境：jdk1.8+maven3.6.0+MySQL5.7+nodejs14.21.3+Redis
服务端技术：Springboot+Mybatis-Plus
前端技术：html+css+Vue+axios+Element-UI
## 成果展示
文档展示
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/3bbfc9fddf944afeacfb3198c9096a30.png)
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/ea9bfa42bcb649779e2924c614303c68.png)
用户登录
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/b0c3a235b3a24dc4a39b3421debc8636.png)
管理员首页
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/7e9fdb0e37bc459c89074a009282e4a3.png)
医生信息管理
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/070e9a347a1444e596cb7accab520c9c.png)
患者信息管理
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/5f03f7c1c6c742118482df4d06c78a9d.png)

挂号信息管理
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/32eff86eec7a4adcaf06639c1467a86c.png)

药物信息管理
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/020c74f268984fd69f07434efe5b7ad7.png)

检查项目管理
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/009f1e5037d34972b3e05d43fadcb1c5.png)

病床信息管理
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/e0164d1904474cf5bab4b385392cb189.png)

排班信息管理
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/a5ac6d50a8a74939a2d8228820348c44.png)

数据统计分析
![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/da46987e90a24818a1cd0c1fa9f0f578.png)

源码展示

```c
@RestController
@RequestMapping("admin")
public class AdminController {

    @Autowired
    private AdminService adminService;
    @Autowired
    private DoctorService doctorService;
    @Autowired
    private PatientService patientService;
    @Autowired
    private OrderService orderService;

    /**
     * 登录数据验证
     */
    @PostMapping("/login")
    @ResponseBody
    public ResponseData login(@RequestParam("aId") int aId, @RequestParam("aPassword") String aPassword) {
        Admin admin = this.adminService.login(aId, aPassword);
        if (admin != null) {
            Map<String,String> map = new HashMap<>();
            map.put("aName", admin.getAName());
            map.put("aId", String.valueOf(admin.getAId()));
            String token = JwtUtil.getToken(map);
            map.put("token", token);
            return ResponseData.success("登录成功", map);
        } else {
            return ResponseData.fail("登录失败，密码或账号错误");
        }
    }

    /**
     * 分页模糊查询所有医护人员信息
     */
    @RequestMapping("findAllDoctors")
    public ResponseData findAllDoctors(@RequestParam(value = "pageNumber") int pageNumber, @RequestParam(value = "size") int size, @RequestParam(value = "query") String query){
        return ResponseData.success("返回医护人员信息成功",  this.doctorService.findAllDoctors(pageNumber, size, query));
    }
    /**
     * 根据id查找医生
     */
    @RequestMapping("findDoctor")
    public ResponseData findDoctor(@RequestParam(value = "dId") int dId) {
        return ResponseData.success("查询医生成功", this.doctorService.findDoctor(dId));
    }
    /**
     * 增加医生信息
     */
    @RequestMapping("addDoctor")
    @ResponseBody
    public ResponseData addDoctor(Doctor doctor) {
        Boolean bo = this.doctorService.addDoctor(doctor);
        if (bo) {
            return ResponseData.success("增加医生信息成功");
        }
        return ResponseData.fail("增加医生信息失败！账号或已被占用");
    }
    ...
}
```

![在这里插入图片描述](https://i-blog.csdnimg.cn/direct/f2728c3f61b445fb8c1f10411cb41fd0.png)
## 为什么选择我？

> 博主本身也是从大学走出来的，所有编程知识都是自己一点一点学来的，没有实战项目经验，多亏有前辈收取少量费用就提供项目和讲解，才获得了工作机会，吃水不忘挖井人，博主现在从事开发软件开发、有丰富的编程能力和水平、也学习前辈帮助更多需要帮助的人学习编程！少走弯路！

## 源码获取：
weixin :  a1719101159
