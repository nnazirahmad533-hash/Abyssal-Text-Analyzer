from collections import Counter

def abyssal_text_analyzer(text1, text2):
    # 🧹 Preprocessing: Remove non-alphanumeric characters and lowercase
    cleaned_text1 = "".join(char.lower() for char in text1 if char.isalnum())
    cleaned_text2 = "".join(char.lower() for char in text2 if char.isalnum())
    
    if not cleaned_text1 or not cleaned_text2:
        return None, None, "Error: Inputs must contain alphanumeric characters."

    # 🔄 Palindrome check on text2
    is_palindrome = cleaned_text2 == cleaned_text2[::-1]
    
    # 🔤 Anagram / Substring check using Counter and sliding window
    c1 = Counter(cleaned_text1)
    c2 = Counter(cleaned_text2)
    
    is_anagram_pattern = False
    
    # Check if text2 can be formed from a window in text1 or matches frequency constraints
    if len(cleaned_text2) <= len(cleaned_text1):
        k = len(cleaned_text2)
        window_counter = Counter(cleaned_text1[:k])
        
        if window_counter == c2:
            is_anagram_pattern = True
        else:
            for i in range(k, len(cleaned_text1)):
                # Slide the window
                start_char = cleaned_text1[i - k]
                end_char = cleaned_text1[i]
                
                window_counter[start_char] -= 1
                if window_counter[start_char] == 0:
                    del window_counter[start_char]
                
                window_counter[end_char] += 1
                
                if window_counter == c2:
                    is_anagram_pattern = True
                    break

    return is_palindrome, is_anagram_pattern, None

def main():
    print("=========================================")
    print("    🌌 ABYSSAL TEXT ANALYZER 🌌    ")
    print("=========================================")
    
    while True:
        print("\n[Menu]")
        print("1. Analyze text pair")
        print("2. Exit")
        
        choice = input("Select an option (1 or 2): ").strip()
        
        if choice == '2':
            print("\nExiting Abyssal Text Analyzer. Goodbye! ✨")
            break
        elif choice == '1':
            t1 = input("\nEnter Base Text (text1): ")
            t2 = input("Enter Target Text (text2): ")
            
            palindrome_res, anagram_res, error = abyssal_text_analyzer(t1, t2)
            
            if error:
                print(f"\n❌ {error}")
                continue
                
            print("\n-----------------------------------------")
            print("📊 ANALYSIS RESULTS:")
            print(f"• Palindrome Check (Target): {'✅ Passed' if palindrome_res else '❌ Failed'}")
            print(f"• Anagram/Window Match:     {'✅ Passed' if anagram_res else '❌ Failed'}")
            
            # Final result condition (as in your original logic)
            final_match = palindrome_res and anagram_res
            print(f"\n🔍 Final Match Found: {final_match}")
            print("-----------------------------------------")
        else:
            print("\n⚠️ Invalid option. Please enter 1 or 2.")

if __name__ == "__main__":
    main()
