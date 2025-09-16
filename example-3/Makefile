# Makefile для игры Kazino-Royal  
# Игра в кости с тремя попытками

.PHONY: all debug release clean help test

# Определяем компилятор C++
CXX = g++

# Флаги компиляции  
CXXFLAGS = -Wall -Wextra -pedantic -std=c++17  
RELEASE_FLAGS = -O2 -DNDEBUG  
DEBUG_FLAGS = -g -O0 -DDEBUG

# Имена исполняемых файлов  
RELEASE_EXEC = kazino-royal  
DEBUG_EXEC = kazino-royal-dbg

# Исходные файлы  
SOURCES = Kazino-Royal.cpp

# Цели по умолчанию  
all: release

# Release сборка  
release: CXXFLAGS += $(RELEASE_FLAGS)  
release: $(RELEASE_EXEC)

# Debug сборка  
debug: CXXFLAGS += $(DEBUG_FLAGS)
debug: $(DEBUG_EXEC)

# Сборка release версии  
$(RELEASE_EXEC): $(SOURCES)
    $(CXX) $(CXXFLAGS) $(SOURCES) -o $(RELEASE_EXEC)

# Сборка debug версии  
$(DEBUG_EXEC): $(SOURCES)
    $(CXX) $(CXXFLAGS) $(SOURCES) -o $(DEBUG_EXEC)

# Очистка  
clean:
    rm -f $(RELEASE_EXEC) $(DEBUG_EXEC)

# Информация о сборке  
info:
    @echo "Компилятор: $(CXX)"
    @echo "Флаги release: $(RELEASE_FLAGS)"
    @echo "Флаги debug: $(DEBUG_FLAGS)"
    @echo "Исходные файлы: $(SOURCES)"
    @echo "Цели: all debug release clean info"

# Справка  
help: info  
    @echo "Использование:"
    @echo "  make       - собрать release версию"
    @echo "  make debug - собрать debug версию"
    @echo "  make clean - удалить скомпилированные файлы"
    @echo "  make info  - показать информацию о сборке"
    @echo "  make help  - показать эту справку"

# Тестирование (добавьте свои тесты)
test: debug  
    @echo "Запуск тестовой версии..."
    @./$(DEBUG_EXEC) test
