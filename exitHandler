#include <iostream>
#include <cstdlib>
#include <thread>
#include <chrono>

// 가상의 라이브러리 함수
void libraryFunction() {
    std::cout << "라이브러리 함수가 호출되었습니다." << std::endl;
    exit(1); // 프로그램 종료
}

// 종료 처리 함수
void exitHandler() {
    std::cout << "프로그램이 종료됩니다." << std::endl;
}

// 스레드에서 실행될 함수
void threadFunction() {
    libraryFunction();
}

int main() {
    // atexit를 사용하여 종료 처리 함수 등록
    std::atexit(exitHandler);
    
    // 스레드 생성 및 실행
    std::thread t(threadFunction);
    
    // 메인 스레드는 여기서 다른 작업을 수행할 수 있음
    std::this_thread::sleep_for(std::chrono::seconds(1));
    
    // 스레드 종료 대기
    t.join();
    
    return 0;
}
