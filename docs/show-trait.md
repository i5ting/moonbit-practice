```moonbit
// 1) 定义联合类型
priv enum IntOrStr {
  Int(Int)
  Str(String)
}
///|
impl Show for IntOrStr with
  output(self : IntOrStr, logger : &Logger) -> Unit {
  match self {
    Int(n) => {
      logger.write_string("Int(")
      logger.write_object(n)
      logger.write_string(")")
    }
    Str(s) => {
      logger.write_string("Str(\"")
      logger.write_string(s)
      logger.write_string("\")")
    }
  }
}
///|
fn main {
  let arr: Array[IntOrStr] = Array::new()
  // 3) 插入不同类型的元素
  arr.push(Int(42))
  arr.push(Str("hello"))
  // 4) 使用时做模式匹配
  for x in arr.iter() {
    println(x)
  }
}

```