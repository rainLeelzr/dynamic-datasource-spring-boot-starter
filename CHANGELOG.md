# v3.3.3

- feat:重要更新-Druid不用再手动排除。

# v3.3.2

- feat:重要更新-支持无数据源启动，支持配置懒启动数据源。
- refactor:重要更新-Druid不再默认启动wall的filter。
- refactor:重要更新-DataSourceCreator移除含有publicKey的方法，由DefaultDataSourceCreator传递。
- refactor:DefaultDataSourceCreator独立不继承DataSourceCreator。
- refactor:简化本地事务ThreadLocal。
- feat: 健康检查优化。
- style:license format。
- chore:remove travis。

# v3.3.1

- fix: 修复打包后强制依赖seata报错。

# v3.3.0 BUG版本不能使用

- feat:重要：本地多数据源事物支持。 @FUNKYE
- feat:底层数据源保存方式修改为ConcurrentHashMap。 @刘尚
- revert:重构底层Creator的创建规则。@刘尚
- feat:添加同名数据源覆盖老数据源。@刘尚
- feat:支持部分从接口继承DS的场景。@CQJames
- fix:修复Druid防火墙一个参数设置错误。@mrf
- fix:修复极端情况下的设置数据源异常处理。@happier233

# v3.2.1

- 提供注解查找非public方法的扩展。 @刘尚
- 修复数据源关闭的错误。 @zuihou
- 修复创建ItemDatasource参数错误。
- 修复自定义注解在方法上失效。
- 添加默认的Master和Slave注解。
- 示例项目整体迁出为独立项目https://gitee.com/baomidou/dynamic-datasource-samples 。

# v3.2.0

- 支持通配符扫描schema文件。 @superlyao
- 支持配置driverClassName为非必须属性。@Hccake
- 支持独立配置每个库的p6spy和seata的开启状态。
- 修复druid设置超时回收时间方法错误。 @liupeng
- 支持自定义注解，需继承DS。 @liupeng
- 修复spring.aop.auto=false下不支持问题。 @刘尚
- 修复多层代理无法获取InvocationHandler的实现类的问题。 @刘尚
- 修复mybatisPlus3下直接调用lamba方法不支持问题。 @刘尚
- seata集成优化和示例项目更新1.3.0。  @a364176773
- 调用DataSourceCreator创建的数据源会包装成ItemDataSource，存储原dataSource和包装后的dataSource。
- DynamicRoutingDataSource内部关闭数据源优化。
- breakChange: 去除以前的实验性功能，如正则切换。
- 示例项目新增quartz和sharding-jdbc的集成。
- 示例项目整体更新。

# v3.1.1

- revert: 不使用NamedInheritableThreadLocal。
- 设置默认spel解析方式为空,提供set方法可重定义解决复杂场景spel表达式问题。
- 格式化正式工程为IDEA默认格式化方案。
- 部分日志等级降低为debug。
- druid部分日志添加集成引导。

# v3.1.0 BUG版本不能使用

- 删除数据源不允许删除主数据源。
- 使用NamedInheritableThreadLocal。
- 增加druid参数queryTimeOut配置。
- 模块化creator和注册为BEAN。

# v3.0.0

- 支持 seata 分布式事务。
- creator 模块化改造。
- 解决启动类判断druid自动配置冲突问题。

# v2.5.8

- spel切换下的空指针异常处理。
- pollName优先使用外部配置。
- 支持classpath开头的schema。
- 取消自动数据源监测，后续需要手动开启。
- 新增druid的slf4j的简单配置。
- 支持集成seata。
- 内部模块化的更好分层。

# v2.5.7

- 优化底层map存储初始化大小。
- 支持数据源变化监控，基于actuator。
- 优化主从分离插件内部逻辑。

# v2.5.6

- 支持非web环境启动。
- 支持加密自定义公钥和全局公钥。
- 启动初始化数据默认分隔符改为分号 `;`  。
- google代码格式化。
- 添加从数据库初始加载数据源例子。

# v2.5.5

- 支持非web环境启动。
- 支持内置加密。
- 支持启动ddl  schema和data。

# v2.5.4

- 集成druid支持配置proxyFilter。
- 修复打war包外部部署错误。
- 修复内置的读写分离插件错误。
- 修复关闭数据源异常。
- 修复日志打印小错误。
- 新增严格模式。

# v2.5.3

- 自定义切面支持动态解析。 https://github.com/baomidou/dynamic-datasource-spring-boot-starter/pull/29

# v2.5.2

- 解决对mp3.1.0的支持。

# v2.5.1

- 工具类新增清空本地线程的方法。
- 优化对p6spy的支持。
- 新增在Mybatis环境下的纯读写分离插件，无需注解。
- 新增关闭数据源的destroy方法。
- 完善druid的wall和stat的配置支持。

# v2.5.0

- 修复数据源启动说明错误。
- 修复负载均衡策略切换隐藏bug。
- 底层更换为ArrayDeque。
- 重构动态处理器。

# v2.4.2

- 引入了实验性的功能： 根据正则或spel来自动匹配数据源。

# v2.4.1

- 修复了上个版本hikari不兼容1.5.x的BUG。
- 提供了hikari全局属性的配置。

# v2.4.0
- 重构了druid配置。
- 支持了更多druid参数配置，支持了加密。
- 完善了文档。

# v2.3.6 
- 修复上个版本的druid参数设置bug。
- 对外开放获取所有数据源和所有组数据源方法。

# v2.3.5 druid参数设置有bug
- 支持p6sy。(格式化sql利器)
- 支持jndi数据源。
- 支持druid更多参数。
- 支持hikari参数设置。
- 切换数据源工具类只有在clear的时候才移除当前数据源名称。
- 启动带上数据源名称。
- 添加了更多的测试代码。

# v2.3.4
- 底层细节优化。
- 重构多级数据源切换。
- 示例项目重构。

# v2.3.3 BUG版本不能使用
- 支持嵌套下多级的数据源切换(service1 mysql调用service2 oracle)。

https://gitee.com/baomidou/dynamic-datasource-spring-boot-starter/issues/IO33C

- 修复spel对request和session的支持。

# v2.3.2 BUG版本不能使用
- 修复在不需要session的场景中自动注入session。

# v2.3.1 BUG版本不能使用
- 修复2.3.0中使用spel session 和header的取值错误。

# v.2.3.0

- 重构创建数据源类。废弃DataSourceFactory，改为Bean的DynamicDataSourceCreator。
- 自动适配mybatisPlus，移除参数的mp-enabled。
- 新特性支持spel参数获取数据源。

# v2.2.3

- 支持druid参数全局配置。
- 对外暴露动态添加删除数据源的方法。
- 增加在组内数据源为空时使用默认数据源。
- 去除启动时校验组内只有单个数据源。

# v2.2.2 BUG版本不能使用

- 修复上个版本mp3适配失败的Bug。

# v2.2.1

- 适配mybatis2.x版本。

# v2.2.0

- 修复从默认数据源获取数据不能是组数据源的bug。
- 摒弃spring原生动态数据源抽象，重新实现。
- 去除底层方法缓存。
- 提供从JDBC中获取数据源的抽象。
- 部分代码重新划分包。
- license的组织名更新成为baomidou。

# v2.1.1

- 切面顺序调整为最高。
- 底层切换数据源逻辑优化。

# v2.1.0

- 修复了底层一个逻辑bug。
- 提供了对mp的原生支持。
- 底层代码进行了细微的性能优化。

# v2.0.2

- 修复springboot2.0以上版本不能设置HikariDataSource。
- 底层代码的整理。
- Druid数据源初始大小改为3。

# v2.0.1

- 修复一个方法缓存的bug，会引起同名方法的注解失效。
- 底层代码的重命名和部分格式的调整。

# v2.0.0

- Breaking change：数据源配置同级，不再默认主从，支持多种方案。
- Breaking change：使用约定大于配置，开启 多组模式 新启程。
- Breaking change：注解包路径变更，与苞米豆其他项目保持一致写法。
- Breaking change：不再支持@DS空注解。
- Breaking change：不再支持强制主库force-master配置。
- Breaking change：数据源选择策略现在如需更改需要设置配置文件的dynamicDataSourceStrategyClass。
- Druid数据源默认validation-query 为select 1 。
- 全部源码改为中文。
- 增加了部分启动时和运行中的日志。

# v1.4.0

- 支持了在类上注解，如果方法上同时有注解则方法注解优先。
- 支持了遇到事物强制主库，并且是默认行为，可在配置更改foeceMaster。
- 最低支持jdk1.7，springboot1.4.x。
- 重构aop，解决了部分springboot版本引入插件无效的问题。

# v1.3.0

- 对Druid的paCache属性提供支持。
- 还原上一版本切面的配置方式。
- 其他一些细节的优化。

# v1.2.0

- 对Druid提供更完善的支持。
- 更改了默认的注解切面的注入方式。
- 抽象了切面选择数据源接口，方便以后支持spel语法等。

# v1.1.0

- 支持Druid数据源 (support DruidDataSource)。
