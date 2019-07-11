# GeneratorSqlMapCustom
仅需要修改Generatorconfig.xml中的数据库连接参数，和生成Pojo类位置，生成Mapper接口位置，生成Mapper映射文件位置以及指
定数据库表名即可，修改好之后运行GeneratorSqlmap.java，然后刷新项目就会出现对应的包，复制到所需项目即可

# 数据库连接参数
   // 数据库连接的信息：驱动类、连接地址、用户名、密码,这里配置的是mysql的，当然也可以配置oracle等数据库
        <jdbcConnection driverClass="com.mysql.jdbc.Driver"
            connectionURL="jdbc:mysql://localhost:3306/myproject" userId="root"
            password="12345">
        </jdbcConnection>
        
# 生成Pojo类位置，Mapper接口位置和Mapper映射文件位置
        //targetProject:生成PO类的位置
        <javaModelGenerator targetPackage="cn.myproject.pojo"
            targetProject=".\src">
            <!-- enableSubPackages:是否让schema作为包的后缀 -->
            <property name="enableSubPackages" value="false" />
            <!-- 从数据库返回的值被清理前后的空格 -->
            <property name="trimStrings" value="true" />
        </javaModelGenerator>
        //targetProject:mapper映射文件生成的位置 
        <sqlMapGenerator targetPackage="cn.myproject.mapper"
            targetProject=".\src">
            <!-- enableSubPackages:是否让schema作为包的后缀 -->
            <property name="enableSubPackages" value="false" />
        </sqlMapGenerator>
        //targetPackage：mapper接口生成的位置 
        <javaClientGenerator type="XMLMAPPER"
            targetPackage="cn.myproject.mapper" targetProject=".\src">
            <!-- enableSubPackages:是否让schema作为包的后缀 -->
            <property name="enableSubPackages" value="false" />
        </javaClientGenerator>
        
# 指定数据库表名
        // 指定数据库表
        <table tableName="user"></table>
        <table tableName="applicantinfo"></table>
        <table tableName="bossinfo"></table>
        <table tableName="companyinfo"></table>
        <table tableName="desiredposition"></table>
        <table tableName="educationexperience"></table>
        <table tableName="imgurl"></table>
        <table tableName="message"></table>
        <table tableName="workexperience"></table>
        <table tableName="onlineresume"></table>
        <table tableName="projectexperience"></table>
        <table tableName="positioninfo"></table>
        
 
