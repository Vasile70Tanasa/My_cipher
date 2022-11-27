Step 1

MyCipher splits the original text în two substrings: the first one is composed of characters having even indices in the original text and the second from characters having odd indices in the original text.

Ex: original text = ‘abcdef’
first string = ‘ace’ (indices: 0, 2, 4)
second string = ‘bdf’ (indices: 1, 3, 5)

Then, it reverses the second string and joins it with the first.
Ex: Step1 result = ‘ace’ + ‘bdf’ inversed = ‘ace’ + ‘fdb’ = ‘acefdb’

Step 2

For this step, MyCipher uses a key and an alphabet.

The key is the length of the original text. For the above example key = 6.
The alphabet is made up of alternating the letters from ascii_lowercase and ascii_uppercase.

ascii_lowercase = ‘abcdefghijklmnopqrstuvwxyz’

ascii_uppercase = ‘ABCDEFGHIJKLMNOPQRSTUVWXYZ’

The resultant alphabet is ‘aAbBcCdDeEfFgGhHiIjJkKlLmMnNoOpPqQrRsStTuUvVwWxXyYzZ’, having 52 characters.

Then, the cipher takes the alphabet index value of every character in the original text and adds the value of the key.

For example, the character 'd' has an index value of 6 in the alphabet, and adding 6 (the key) gives 12, which is 'g' in the alphabet.

Values greater than 52 or less than 0 are "wrapped around", and start at the other side of the alphabet, so a -1 is considered a 51, and a 52 is considered a 0.

If a character in the original text is not in the alphabet, it is simply left unchanged.

In this way, the string ‘acefdb’ becomes ‘dfhige’.

For decryption, the decipher follows the same steps in reverse.
