# LimeBean

[![Build status](https://ci.appveyor.com/api/projects/status/o3lauspwhfk898o7?svg=true)](https://ci.appveyor.com/project/AlekseyMartynov/limebean)
[![Build Status](https://travis-ci.org/AlekseyMartynov/LimeBean.svg)](https://travis-ci.org/AlekseyMartynov/LimeBean)

[RedBeanPHP](http://redbeanphp.com/)-inspired data access layer for .NET and Mono.

## Supported Databases
* MySQL/MariaDB
* SQLite
* SQL Server

## Synopsis

LimeBean treats your data entities as `IDictionary<string, IConvertible>` and maintains the database schema on the fly (when in fluid mode).

LimeBean does not use any Reflection, IL emitting, `dynamic`, etc. Instead it relies on strings, dictionaries and fragments of plain SQL.  

## Code Samples

* [Untyped CRUD](https://github.com/AlekseyMartynov/LimeBean/blob/master/LimeBean.Tests/Examples/Crud.cs)
* [Strongly-typed models with inter-bean links and lifecycle hooks](https://github.com/AlekseyMartynov/LimeBean/blob/master/LimeBean.Tests/Examples/Northwind.cs)
* [Usage in ASP.NET](https://github.com/AlekseyMartynov/LimeBean/blob/master/LimeBean.Tests/Examples/AspNet.cs)
* [GUID primary keys](https://github.com/AlekseyMartynov/LimeBean/blob/master/LimeBean.Tests/Examples/AutoGuidKeys.cs)

## API

All available properties and methods are exposed via the [BeanApi facade class](https://github.com/AlekseyMartynov/LimeBean/blob/master/LimeBean/BeanApi.cs).

## Limitations and Cautions

* Non thread-safe: use one API instance per thread, or maintain thread synchronization with locks. Read-only access is not thread-safe either because of the internal LRU cache.
* Property values must be `IConvertible`. Any other values have to be stored as strings.

## License

* The contents of the [LimeBean directory](https://github.com/AlekseyMartynov/LimeBean/tree/master/LimeBean) and the produced assembly **bin/LimeBean.dll** are licensed under the [MIT license](https://github.com/AlekseyMartynov/LimeBean/blob/master/LimeBean/LICENSE.txt).
* Any other files (unit tests, etc) are for development and testing purposes only.