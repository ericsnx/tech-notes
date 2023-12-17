1. **Creation:** A goroutine is created using the `go` keyword followed by a function call or an anonymous function. Once created, it's managed by the Go runtime scheduler.

2. **Ready:** After creation, the goroutine is in a "ready" state, waiting for the scheduler to allocate resources and schedule it for execution. At this point, it's ready to run but might not be actively executing.

3. **Running:** When the scheduler assigns processor time to the goroutine, it enters the "running" state and starts executing the code within the function.

4. **Blocked/Waiting:** A goroutine can move from the running state to a "blocked" or "waiting" state when it encounters certain conditions like waiting for I/O operations, synchronization with channels, or for a specific event to occur. While blocked, it doesn’t consume CPU time, allowing other goroutines to be scheduled.

5. **Termination:** A goroutine terminates when it reaches the end of its function, encounters a `return` statement, or if the `runtime.Goexit()` function is called. When a goroutine ends, resources associated with it, like memory, are released.

6. **Garbage Collection:** After termination, any resources allocated by the goroutine are marked for garbage collection, and when appropriate, the garbage collector reclaims that memory.

This lifecycle is somewhat abstract and dynamic, as goroutines can move between these states dynamically based on the scheduling decisions made by the Go runtime.

Visualizing this as a diagram might involve boxes representing different states (ready, running, blocked, terminated) with arrows indicating transitions between these states based on the program's execution and scheduler decisions. However, since goroutines can be created, scheduled, and terminated dynamically, it's more like a continuous flow than a fixed sequence of steps.