# new-multichain-bonding
I am a Senior Cryptography Developer with experience in crypto-fund projects at NevaVentures 
#include <iostream>
#include <thread>
#include <mutex>

int main() {
    std::mutex mtx;

    std::thread t1([&]() {
        mtx.lock(); // Блокировка мьютекса
        std::cout << "Поток 1 начал работу" << std::endl;
        mtx.unlock(); // Разблокировка мьютекса
    });

    std::thread t2([&]() {
        mtx.lock(); // Блокировка мьютекса
        std::cout << "Поток 2 начал работу" << std::endl;
        mtx.unlock(); // Разблокировка мьютекса
    });

    t1.join(); // Ожидание завершения работы потока 1
    t2.join(); // Ожидание завершения работы потока 2

    return 0;
}
