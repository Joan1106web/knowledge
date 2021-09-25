# ts（ts 是 js 的一个超集和扩展，主要用来定义和规范 js）

---

### 联合类型

- 类型定义：取值为定义类型中的一种，使用|进行分割

```
type unionType1 = string |number;

interface A{
    name:string;
    age:number;
}
interface B{
    name:string;
    sex:string;
}
type unionType2 = A | B;
```

### 交叉类型

- 类型定义：多个类型合并为一个类型，取所有类型的并集

```
interface A{
    name:string;
    age:number;
}
interface B{
    name:string;
    sex:string;
}
let a:A & B = {
    name:'雨虔',
    age: 27,
    sex: '女'
}
```

### 高级类型

- Partial（将必有类型转为可选类型，不适用 type）

```
interface A {
    name:string;
    age:number;
}
type B = Partial<A>; // 类型B与C等价
type C = {
    name?:string;
    age?:number;
}
```

- Required（将可选类型转为必有类型，与 Partial 互斥，不适用 type）

```
interface A {
    name?:string;
    age?:number;
}
type B = Required<A>; // 类型B与C等价
type C = {
    name:string;
    age:number;
}
```

- Readonly（将所有类型转为只读类型，不适用 type）

```
interface A {
    name:string;
    age:number;
}
type B = Readonly<A>;
let b:B={
    name:'雨虔',
    age:27
}
b.age = 28; // 该语句会报错
```

- Pick（从泛型中提取属性，组成一个新的类型,不适用 type）

```
interface A{
    name:string;
    age:number;
    sex:string;
}
type B = Pick<A,'name'| 'age'>; // 类型同C
interface {
    name:string;
    age:number;
}
```

- Record（将一个类型的属性映射到另一个类型的属性，可结合 type 和 interface 一起使用）

```
type A = '张三' | '李四' | '王五';
type B = Record<A:{name:string,age:number}>; // 类型同C
interface C ={
    '张三':{
        name:string;
        age:number;
    },
    '李四':{
        name:string;
        age:number;
    },
    '王五':{
        name:string;
        age:number;
    }
}
```

- Exclude（删除 T 中的类型，剩余将组成一个新类型 U，不适用 interface）

```
type A = '张三' | '李四' | '王五' | '赵六';
type B = Exclude<A,'李四' | '王五'>; // 类型同C
type C = '张三' | '赵六';
```

- Omit（删除 T 中的属性类型，剩余将组成一个新的类型 U，不适用 type）

```
interface A {
  name: string;
  age: string;
  sex: string;
}
type B = Omit<A, 'age'>; // 类型同C
type C = {
name: string;
  sex: string;
}
```

- Extract（提取 T 和 U 中共有的类型，不适用 interface）

```
type A = '张三' | '李四' | '王五' | '赵六';
type B = '李四' | '孙七';
type C = Extract<A,B>; // 取A、B的交集　
```

- NonNullable（删除泛型 T 中的 null 和 undefined，不适用 type）

```
type A = '张三' | '李四' | null | undefined;
type B = NonNullable<A>; // 类型同C
type C =  '张三' | '李四';
```

- Parameters（以元祖方式获取函数入参类型，最终生成类型均为 type）

```
function A(name:string,age:number){}
type B = Parameters<typeof A>;  // 类型同C
type C = [string,number]
```

- ConstructorParameters（以元祖方式获取构造函数入参类型，最终生成类型均为 type）

```
class A {
    public constructor(name:string,age:number){}
}
type B = ConstructorParameters<typeof A>; // 类型同C
type C = [string,number]
```

- ReturnType（获取函数返回值类型，最终生成类型均为 type）

```
function A(name:string,age:number){
    return name;
}
type B = ReturnType<typeof A>;// 类型同C
type C = string;
```

- InstanceType（获取构造函数实例类型，最终生成类型均为 type）

```
class A {
  public constructor(name: string) { }
}
type B = InstanceType<typeof A>;
```
