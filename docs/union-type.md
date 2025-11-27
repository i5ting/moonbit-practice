// 1) 定义联合类型
enum IntOrStr {
  Int(int)
  Str(string)
}

// 2) 声明数组（动态数组为例）
let mut arr: Array<IntOrStr> = Array::new()

// 3) 插入不同类型的元素
arr.push(Int(42))
arr.push(Str("hello"))

// 4) 使用时做模式匹配
for x in arr.iter() {
  match x {
    Int(n) => {
      // 处理 int 分支
    }
    Str(s) => {
      // 处理 string 分支
    }
  }
}