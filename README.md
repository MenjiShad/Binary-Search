Binary-Search
=============

Binary Search Algorithm for ArrayList of Integers
import java.util.ArrayList;

public class Binary_Search
{
  public int elementFinder(ArrayList<Integer> list, int searchNum)
  {
    System.out.println("Binary Search has been called.");
    int foundLocation;
    // left endpoint of the search interval
    int i = 1;
    // right endpoint of the search interval
    int j = list.size()-1;
    int searchIndex; // As the binary search searches halves, this is to keep track of the new starting index
    // While there are two segments to search, run the block
    while (i < j)
    {
      // New searchIndex is equal to the midpoint between i's index and j's index rounded down
      searchIndex = (int) Math.floor((i+j)/2);
      // If the Requested Search Value is greater than the midpoint's value
      if (searchNum > list.get(searchIndex))
      {
        i = searchIndex + 1; // Search the second segment, since the value will be in the larger block
      }
      else
      {
        j = searchIndex; // Search the first segment, since the value will be in the smaller block
      }
    }
    // Once the search reduces down to one value, check if the requested search value is the same as the final value
    if (searchNum == list.get(i))
    {
      foundLocation = i; // if it's the same, return the index of the value
    }
    else
    {
      foundLocation = -1; // if it's not same, return -1
    }    
    return foundLocation;
  }
}
