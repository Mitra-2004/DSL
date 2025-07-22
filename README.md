customer_ids = [1001,2004, 2400,1491, 1233, 1456, 1981]

def linear_search(ids, target_id):
    for i in range(len(ids)):
        if ids[i] == target_id:
            return True
    return False
def binary_search(ids, target_id):
    ids.sort()  
    low = 0
    high = len(ids)-1

    while low <= high:
        mid = (low + high)// 2
        if ids[mid] == target_id:
            return True
        elif ids[mid] < target_id:
            low = mid + 1
        else:
            high = mid - 1

    return False
print("Customer Account ID List:", customer_ids)
search_id = int(input("Enter the customer account ID to search: "))
found_linear = linear_search(customer_ids, search_id)
print("\nUsing Linear Search:")
print("ID Found ✅" if found_linear else "ID Not Found ❌")

found_binary = binary_search(customer_ids, search_id)
print("\nUsing Binary Search:")
print("ID Found ✅" if found_binary else "ID Not Found ❌")
