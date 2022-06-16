## RecyclerView

### Theory

At the moment, the history fragment shows the list of values in a simple textview. Not very shiny! In this section, we will therefore enable the user to scroll through a large list of values. Now imagine you have a very long list of values. You don't want the app to generate the views for all these values when you can show only a small number at the same time on the screen. Instead, you want to free views when the user scrolls them out of sight and generate new ones on the fly, i.e. you want to reuse (recycle!) the views. And this is exactly what the [RecyclerViews](https://developer.android.com/guide/topics/ui/layout/recyclerview) is made for! Coding a RecyclerView mainly consists of three steps:
1. Design how a single item should look like (using the standard xml approach).
2. Tell the app how it should put your data into the design (generate an adapter).
3. Add the recyclerview to your fragment and tell it that it should use the adapter.

So, let's walk through this in detail! As we use View Binding, the code deviates a bit from the standard approach shown in the documentation.

#### Single Item

That's easy. Just right-click on the layout folder (in the res folder) and generate a 'New' -> 'Layout Resource File'. Add whatever UI elements you want to see in a single element. Importantly, choose 'wrap-content' for your layout_height.

#### Build an Adapter

Generate a 'New' -> 'Kotlin Class/File' in a suitable Kotlin Code directory. To easily see that it is an adapter, you might want to add 'Adapter' to the name of the file. The property of this new class is the list of objects you want to show. To tell Kotlin that this class is a RecyclerView Adapter, let it inherit from 'RecyclerView.Adapter'. In addition, you have to give Kotlin a type for this Adapter. Here, we make use of a new concept. The type is itself a new class, which we generate in the Adapter class. Sounds weird, but here's an example code:

    class HistoryAdapter(private val historyList: List<Int>) : 
        RecyclerView.Adapter<HistoryAdapter.HistoryViewHolder>() {
    }

Here, 'historyList' contains our data. It's just a list of integers, but you can have more complex objects here. In the type definition of the adapter, we use the class 'HistoryViewHolder', which can be found in ('.') the class HistoryAdapter, which happens to be the class we are just writing. This new class has to inherit from 'RecyclerView.ViewHolder'. As we are using viewbinding, it takes as a parameter the view binding for a single item. As I named the xml layout file 'history_item.xml', the binding is named 'HistoryItemBinding'. This gives us the following class definition, which has to be added into the HistoryAdapter class:

    class HistoryViewHolder(val itemBinding: HistoryItemBinding) : 
        RecyclerView.ViewHolder(itemBinding.root)

Finally, we have to implement three methods of the parent class. As always, we use the override keyword. 

    // This is always the same, just adapt the name of your parentclass and your view binding
    override fun onCreateViewHolder(parent: ViewGroup, viewType: Int): HistoryViewHolder {
        val binding = HistoryItemBinding.inflate(
            LayoutInflater.from(parent.context), parent, false)
        return HistoryViewHolder(binding)
    }

    override fun onBindViewHolder(holder: HistoryViewHolder, position: Int) { 
        // fill your UI elements here.
        // You access the via holder.itemBinding.uiElementName
    }

    override fun getItemCount(): Int {
        // return the size of list you gave as a property to your class
    }

#### Add RecyclerView to Fragment

Now we can add the RecyclerView to the target fragment. First, in the xml Layout, add the RecyclerView and give it a reasonable id. Now head over to the Kotlin Code of the fragment. In the onViewCreated function you have to add the following three lines (adapt naming ;-):

    val historyAdapter = HistoryAdapter(viewModel.numberList)
    binding.rvHistory.adapter = historyAdapter
    binding.rvHistory.layoutManager = LinearLayoutManager(requireContext())

In the first line, you generate an instance of the Adapter class we created above and give it the actual list to display as parameter. In the second you tell the recyclerview to use this adapter. And in the third you tell the recyclerview how it should display the items. The 'LinearLayoutManager' tells the app to show all items underneath each other. You can play around here and substitute it with a GridLayoutManager. This one takes an additional parameter which defines the number of columns you want to see.

### Actions

1. As usual, follow [this video](https://youtu.be/Z7yRgzzUeU8) to implement a recyclerview for the history fragment. Next, see what happens when you substitute the LinearLayoutManager for a GridManager.
2. At the moment, the MainFragment still shows (i) the list of past values and (ii) the number of throws. Both might not be that relevant for a use, especially with the HistoryFragment accessible. So, change the MainFragment to display only the current value! 

---

[back](../README.md)