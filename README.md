# Create-a-Python-script-to-check-for-a-valid-file-path
import os

def is_valid_path(path):
    """
    Checks if the provided path is a valid and existing file or directory.
    
    Args:
        path (str): The file path to check.
        
    Returns:
        bool: True if the path is valid and exists, False otherwise.
    """
    if not path:
        return False
    return os.path.exists(path)

if __name__ == "__main__":
    test_path_1 = "/path/to/nonexistent/file"
    test_path_2 = os.path.join(os.getcwd(), "test_file.txt")
    
    print(f"Is '{test_path_1}' a valid path? {is_valid_path(test_path_1)}")
    
    # Create a dummy file for testing
    with open("test_file.txt", "w") as f:
        f.write("This is a test file.")
        
    print(f"Is '{test_path_2}' a valid path? {is_valid_path(test_path_2)}")
    
    # Clean up the dummy file
    os.remove("test_file.txt")
