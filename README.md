const SIZE: usize = 7; // Визначаємо розмір ромба

fn main() {
    let mut diamond = vec![vec![' '; SIZE * 2 - 1]; SIZE * 2 - 1];

    // Малюємо верхню половину ромба
    for i in 0..SIZE {
        diamond[i][SIZE - 1 - i] = '*';
        diamond[i][SIZE - 1 + i] = '*';
    }

    // Малюємо нижню половину ромба
    for i in 0..SIZE - 1 {
        diamond[SIZE + i][i + 1] = '*';
        diamond[SIZE + i][(SIZE * 2 - 3) - i] = '*';
    }

    // Виводимо ромб одним print!
    print!(
        "{}\n",
        diamond
            .iter()
            .map(|row| row.iter().collect::<String>())
            .collect::<Vec<String>>()
            .join("\n")
    );
}
