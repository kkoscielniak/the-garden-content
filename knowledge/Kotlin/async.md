### The `async()` function

👉 Check [[Knowledge/Kotlin/runBlocking]] code first

```kt
fun main() {
	runBlocking {
		val num1 = async { getValue() }
		val num2 = async { getValue() }
		println("result of num1 + num2 is ${num1.await() + num2.await()}")
	}
}
```

### Output

```
entering getValue() at 22:52:25.025
entering getValue() at 22:52:25.03
leaving getValue() at 22:52:28.03
leaving getValue() at 22:52:28.032
result of num1 + num2 is 0.8416379026501276
```

The two calls to `getValue()` are independent and don't necessarily need the coroutine to suspend. Kotlin has an async function that's similar to launch.

The `async()` function returns a value of type [[Knowledge/Kotlin/Deferred]].

The [[lambda]] passed to `async()` is a [[Knowledge/Kotlin/suspend]] function.
