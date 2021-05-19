Dependency Injection

DRY: Do not repeat yourself.
It requires a Has-a relationship

Example

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
