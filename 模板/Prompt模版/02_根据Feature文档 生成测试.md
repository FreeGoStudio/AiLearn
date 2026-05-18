根据 docs/features/**/*.feature 生成普通 MSTest 单元测试。 
Feature 文件只是行为规范来源，不使用 SpecFlow / Cucumber / Reqnroll。
生成的测试必须先处于 Red 状态，随后再实现业务代码使测试通过。