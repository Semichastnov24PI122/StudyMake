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
	@echo "Стандарт C++: C++17"

# Проверка синтаксиса (без компиляции)
check:
	$(CXX) $(CXXFLAGS) -fsyntax-only $(SOURCES)

# Тестовый запуск с разными сценариями
test: release
	@echo "=== Тестирование игры Kazino-Royal ==="
	@echo ""
	@echo "=== Запуск без ввода (прерывание) ==="
	@echo "Запустите программу и нажмите Ctrl+C для проверки обработки прерывания"
	@echo ""
	@echo "=== Ручное тестирование ==="
	@echo "Запустите: ./$(RELEASE_EXEC)"
	@echo "Попробуйте разные варианты:"
	@echo "  - Правильные числа (1-6)"
	@echo "  - Неправильные числа (0, 7)"
	@echo "  - Нечисловой ввод"
	@echo ""
	@echo "Коды возврата:"
	@echo "  0 - выигрыш (угадал число)"
	@echo "  1 - проигрыш (не угадал за 3 попытки)"
	@echo "  2 - ошибка ввода"

# Установка прав на выполнение
install: release
	chmod +x $(RELEASE_EXEC)
	@echo "Программа готова к выполнению"

# Показать исходный код
source:
	@echo "Содержимое $(SOURCES):"
	@cat $(SOURCES)
