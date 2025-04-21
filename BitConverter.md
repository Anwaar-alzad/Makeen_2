# BitConverter in C#

`BitConverter` in C# is a class provided by the .NET framework that allows you to convert base data types to an array of bytes, and vice versa.  

It’s useful when you need to work with raw binary data, such as when reading from or writing to files, working with sockets, or doing any kind of low-level data manipulation.

## 🔧 Example: Convert `int` to `byte[]` and Back

```csharp
int number = 12345;

// Convert int to byte array
byte[] bytes = BitConverter.GetBytes(number);

// Convert byte array back to int
int restored = BitConverter.ToInt32(bytes, 0);

Console.WriteLine($"Original: {number}, Restored: {restored}");
```
```yaml
Original: 12345, Restored: 12345
```
