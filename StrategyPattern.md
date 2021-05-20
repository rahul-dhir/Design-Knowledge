Strategy pattern
------------------

Whenever we use run time polymorphism, it makes use of strategy pattern. One such example is runtime polymorphism.

**Dependency Injection**
------------------------

DRY: Do not repeat yourself.
It requires a Has-a relationship

Dependency injection is based on the principle "Program for the interface and not for the implementation"

Types of dependency injection
1. Constructor {Used when dependecy exists for the lifetime of the dependent and we cant change the dependcy}
2. Method 
3. Property {Used when the dependency is optional or dependent may come with a dependency but we cna change the dependcy change late

**Example**
------------

class Program
{
static void Main(string[] args)
{
TaskScheduler taskScheduler = new TaskScheduler();
taskScheduler.ScheduleTask(new PriorityQueue(), "FirstTask");
}
}
public class TaskScheduler
{
public void ScheduleTask(IQueueDS taskQueue, string taskName)
{
taskQueue.Enqueue(taskName);
}
}
public interface IQueueDS
{
void Enqueue(string taskName);
void Dequeue();
void ClearQueue();

 }
public class PriorityQueue: IQueueDS
{
private Queue queue;
public PriorityQueue()
{
queue = new Queue();
}
public void Enqueue(string taskName)
{
queue.Enqueue(taskName);
}

 public void Dequeue()
{
queue.Dequeue();
}

 public void ClearQueue()
{
queue.Clear();
}
}



