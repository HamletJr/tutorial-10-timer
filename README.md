# Tutorial 10
**Nama:**   Joshua Montolalu<br>
**NPM:**    2306275746<br>
**Kelas:**  Pengjut A<br>

## Modul 10
### Experiment 1.1
![Gambar eksekusi eksperimen 1](Experiment1.png)
- Dapat dilihat pada gambar bahwa pesan yang ditambahkan, yaitu `Joshua's Komputer: hey hey`, muncul terlebih dahulu. Hal ini terjadi karena perintah `println!()` ditaruh sebelum eksekusi fungsi *async*.
```rs
    println!("Joshua's Komputer: hey hey");

    // Drop the spawner so that our executor knows it is finished and won't
    // receive more incoming tasks to run.
    drop(spawner);

    // Run the executor until the task queue is empty.
    // This will print "howdy!", pause, and then print "done!".
    executor.run();
```
Oleh karena itu, perintah `println!()` yang baru akan dilaksanakan terlebih dahulu secara sinkronus. Setelah itu baru akan dijalankan fungsi *async* oleh Rust. Jika `println!()` ditaruh setelah baris `executor.run()` maka perintah tersebut akan dijalankan setelah fungsi *async* dijalankan. 