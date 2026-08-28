Challenge name  : PW Crack 4 PicoCTF
Category        :Cryptography
Difficulty      :Medium
Description     :Can you crack the password to get the flag?

Download the password checker here
and you'll need the encrypted flag
and the hash
in the same directory too.

There are 100 potential passwords with only 1 being correct. You can find these by examining the password checker script.
Hints
1

A for loop can help you do many things very quickly.
2

The str_xor function does not need to be reverse engineered for this challenge

Dalam analisis saya, Saya membaca seluruh file menggunakan $nano untuk melihat isi dari Password checker dan sesuai dari deskripsi yang meminta agar saya membuat sebuah loop agar memudahkan memecah password yang di berikan.

1. Buka terminal lalu ambil file
   "$wget (file 1) (file 2) (file 3)"
2. Analisis File bernama level4.py menggunakan $nano
3. Perintah di awal meminta untuk membuat sebuah loop maka kita mengedit code python dengan ini

```pos_pw_list = ["158f", "1655", "d21e", "4966", "ed69", "1010", "dded", "844c", "40ab", "a948", "156c", "ab7f", "4a5f", "e38c", "ba12", "f7fd", "d780", "4f4d", "5ba1", "96c5", "55b9", "8a67", "d32b", "aa7a", "514b", "e4e1", "1230", "cd19", "d6dd", "b01f", "fd2f", "7587", "86c2", "d7b8", "55a2", "b77c", "7ffe", "4420", "e0ee", "d8fb", "d748", "b0fe", "2a37", "a638", "52db", "51b7", "5526", "40ed", "5356", "6ad4", "2ddd", "177d", "84ae", "cf88", "97a3", "17ad", "7124", "eff2", "e373", "c974", "7689", "b8b2", "e899", "d042", "47d9", "cca9", "ab2a", "de77", "4654", "9ecb", "ab6e", "bb8e", "b76b", "d661", "63f8", "7095", "567e", "b837", "2b80", "ad4f", "c514", "ffa4", "fc37", "7254", "b48b", "d38b", "a02b", "ec6c", "eacc", "8b70", "b03e", "1b36", "81ff", "77e4", "dbe6", "59d9", "fd6a", "5653", "8b95", "d0e5"]

   def level_4_pw_check():
    for user_pw in pos_pw_list:
        user_pw_hash = hash_pw(user_pw)

        if( user_pw_hash == correct_pw_hash ):
            print("Welcome back... your flag, user:")
            decryption = str_xor(flag_enc.decode(), user_pw)
            print(decryption)
            return
        print("That password is incorrect")
```

   5. Lalu jalankan dengan $python3 level4.py
   6. lalu terminal akan merespons dengan mengeluarkan hasil dari percobaan loop dan flag
   7. dan ini hasilnya Welcome back... your flag, user:
      picoCTF{fl45h_5pr1ng1ng_d770d48c}
