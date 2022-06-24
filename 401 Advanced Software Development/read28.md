
## Recycleview

- Recycle view effiecently displays large sets of data.
- It recycles the individual elements when scrolling through a screen
- Recycle view contains the views corresponding to the data
- A view Holder object is empty on creation Recycle View connects it to data.
- In the adapter the recycle view connects it to the data.
- Layout manager arranges all the elements in the list
- Decide what the list or the grid is going to look like
- Linear layout manager is  a one-dimensional
- GridLayaout manager is a two-dimensional grid
- Staggered GirdlayoutManager doesn't require same width and height
- Once you figured out layout, implement Adapter and ViewHolder

#### 3 methods for Adapter

- `onCreateViewHolder():` Recycleview needs this when it creates a ViewHolder
- `onBindViewHolder():`Recycleview needs this when it needs to associate ViewHolder
- `getItemCount():`Recycleview gets the dataset size

### Example of Adapter and ViewHolder

````Java

public class CustomAdapter extends RecyclerView.Adapter<CustomAdapter.ViewHolder> {

    private String[] localDataSet;

    /**
     * Provide a reference to the type of views that you are using
     * (custom ViewHolder).
     */
    public static class ViewHolder extends RecyclerView.ViewHolder {
        private final TextView textView;

        public ViewHolder(View view) {
            super(view);
            // Define click listener for the ViewHolder's View

            textView = (TextView) view.findViewById(R.id.textView);
        }

        public TextView getTextView() {
            return textView;
        }
    }

    /**
     * Initialize the dataset of the Adapter.
     *
     * @param dataSet String[] containing the data to populate views to be used
     * by RecyclerView.
     */
    public CustomAdapter(String[] dataSet) {
        localDataSet = dataSet;
    }

    // Create new views (invoked by the layout manager)
    @Override
    public ViewHolder onCreateViewHolder(ViewGroup viewGroup, int viewType) {
        // Create a new view, which defines the UI of the list item
        View view = LayoutInflater.from(viewGroup.getContext())
                .inflate(R.layout.text_row_item, viewGroup, false);

        return new ViewHolder(view);
    }

    // Replace the contents of a view (invoked by the layout manager)
    @Override
    public void onBindViewHolder(ViewHolder viewHolder, final int position) {

        // Get element from your dataset at this position and replace the
        // contents of the view with that element
        viewHolder.getTextView().setText(localDataSet[position]);
    }

    // Return the size of your dataset (invoked by the layout manager)
    @Override
    public int getItemCount() {
        return localDataSet.length;
    }
}

````

- [credit](https://developer.android.com/guide/topics/ui/layout/recyclerview#java)

#### Advanced RecycleView Customization

- You add animations by extending the `RecycleView.ItemAnimator`
- `recycleview-selection` is a lirary that enables users to select items in RecycleViewer List

> ## Reference and Citation

> Joshua McCluskey
