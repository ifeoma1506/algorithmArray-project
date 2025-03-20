def sum_of_distinct_elements(set1, set2):
    unique_elements = set(set1) ^ set(set2)  # Symmetric difference to get distinct elements
    return sum(unique_elements)

# Example usage:
set1 = [3, 1, 7, 9]
set2 = [2, 4, 1, 9, 3]
print("Sum of distinct elements:", sum_of_distinct_elements(set1, set2))


def dot_product(v1, v2):
    return sum(x * y for x, y in zip(v1, v2))


def check_orthogonality(vectors):
    results = []
    for v1, v2 in vectors:
        if dot_product(v1, v2) == 0:
            results.append((v1, v2, True))
        else:
            results.append((v1, v2, False))
    return results

# Example usage:
vectors = [([1, 2, 3], [4, -8, 4]), ([2, 3], [-3, 2]), ([1, 0], [0, 1])]
for v1, v2, is_orthogonal in check_orthogonality(vectors):
    print(f"Vectors {v1} and {v2} are {'orthogonal' if is_orthogonal else 'not orthogonal'}")
