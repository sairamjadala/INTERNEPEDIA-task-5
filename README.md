def count_words(text):
    words = text.split()
    return len(words)

def main():
    while True:
        print("Word Count Tool")
        print("1. Input text")
        print("2. Read from file")
        print("3. Quit")

        choice = input("Choose an option: ")

        if choice == "1":
            text = input("Enter text: ")
            try:
                word_count = count_words(text)
                print(f"Word count: {word_count}")
            except Exception as e:
                print("Error:", e)

        elif choice == "2":
            filename = input("Enter filename: ")
            try:
                with open(filename, 'r') as file:
                    text = file.read()
                    word_count = count_words(text)
                    print(f"Word count: {word_count}")
            except FileNotFoundError:
                print("File not found")
            except Exception as e:
                print("Error:", e)

        elif choice == "3":
            break

        else:
            print("Invalid option")

if __name__ == "__main__":
    main()
