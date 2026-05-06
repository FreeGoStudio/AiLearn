# XXX 模块规则

## 模块职责
负责XXX、XXX、XXX、XXX功能。

不负责:
- XXX
- XXX
- XXX

## 分层规则
- Contracts: 只放 DTO / Enums / Request / Response / IAppService接口
- Application：只放 UseCase / Command / Query / DTO / AppService实现
- Domain：只放 Entity / ValueObject / DomainService / DomainEvent / Repository
- Infrastructure：只放 Repository实现 / SQLite查询 / 外部数据源适配

## 禁止

- XXX 模块不能直接引用 XXX 模块的 XXX
- XXX 不能直接访问 XXX
- XXX 不能依赖 XXX 具体实现