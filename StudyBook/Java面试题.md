### Java面试题



### 1.为什么重写 equals 还要重写 hashcode？

在Java中，当你重写`equals()`方法时，通常也需要重写`hashCode()`方法，这主要是基于Java对象在哈希表（如`HashMap`、`HashSet`等）中的行为。这两个方法之间的关联性是Java集合框架的契约所要求的。

1. **equals()方法**：
	`equals()`方法用于比较两个对象是否相等。默认情况下，`equals()`方法继承自`Object`类，它比较的是对象的内存地址（即是否是同一个对象）。在很多情况下，我们需要根据对象的实际内容来判断是否相等，这时就需要重写`equals()`方法。
2. **hashCode()方法**：
	`hashCode()`方法返回对象的哈希码值，这个值通常用于在哈希表中确定对象的存储位置。默认情况下，`hashCode()`方法也继承自`Object`类，它返回的哈希码与对象的内存地址有关。

**为什么需要同时重写这两个方法？**

当我们将对象放入哈希表时，哈希表会根据对象的哈希码值来确定对象在表中的存储位置。如果两个对象根据`equals()`方法是相等的，那么它们的哈希码值也应该相等。这是Java集合框架的一个基本契约。如果违反了这个契约，那么在使用哈希表时可能会出现问题。例如，当你试图从哈希表中检索一个对象时，如果它的哈希码值与表中存储的对象的哈希码值不匹配，那么即使这两个对象根据`equals()`方法是相等的，你也无法从表中检索到它。

因此，当你重写`equals()`方法时，通常也需要重写`hashCode()`方法，以确保这两个方法的行为是一致的。具体来说，如果两个对象根据`equals()`方法是相等的，那么它们的`hashCode()`方法应该返回相同的值；如果两个对象根据`equals()`方法是不相等的，那么它们的`hashCode()`方法应该尽可能返回不同的值（尽管这并不是一个严格的要求，但有助于提高哈希表的性能）。



### 2.**== 和 equals 都是用于比较操作的方法，但它们在多个方面存在显著的区别。**

1. 比较的对象类型

	：

	- == 是一个操作符，它既可以用于比较基本数据类型的值（如 int、char 等），也可以用于比较对象的引用地址，即判断两个对象是否指向内存中的同一位置。
	- equals() 是 Object 类的一个方法，用于比较两个对象的内容是否相等。默认情况下，它比较的是对象的引用地址，但子类可以重写此方法以比较对象的实际内容或属性值。

2. 实现方式

	：

	- == 比较的是两个操作数的值或引用地址，直接进行底层比较。
	- equals() 方法提供了更灵活的比较方式。默认情况下，它比较的是对象的引用地址，但子类可以根据需要重写此方法，以实现基于对象内容的比较。

3. 是否需要重写

	：

	- == 操作符不需要重写，其行为是固定的。
	- equals() 方法通常需要根据实际需要进行重写。例如，在自定义类中，我们通常会重写 equals() 方法，以便正确地比较两个对象的属性值是否相等。

4. 运行速度

	：

	- 由于 == 直接比较值或引用地址，通常它的运行速度会比 equals() 快。
	- equals() 方法可能需要执行更多的操作，特别是当它被重写以执行复杂的比较逻辑时，因此它的运行速度可能会慢一些。

5. 用途

	：

	- == 主要用于基本数据类型的值比较或判断对象引用是否相同。
	- equals() 主要用于判断两个对象的内容或属性值是否相等，这在处理复杂对象时尤为重要。

总的来说，== 和 equals() 在比较对象时有着不同的侧重点和用途。选择使用哪一个取决于你的具体需求，是想要比较对象的引用地址还是实际内容。在编写 Java 代码时，根据具体场景合理地选择和使用这两个方法是非常重要的。