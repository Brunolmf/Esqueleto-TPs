# VARIÁVEIS
CXX       := g++
CXXFLAGS  := -Wall -Wextra -Wpedantic -Wformat-security -Wconversion -Werror -std=c++11

# DIRETÓRIOS
SRC       := src
OBJ       := obj
BIN       := bin
INCLUDE   := include

# ARQUIVOS
SOURCES   := $(wildcard $(SRC)/*.cpp)
OBJECTS   := $(SOURCES:$(SRC)/%.cpp=$(OBJ)/%.o)
EXECUTABLE:= tp2.out

# REGRAS PRINCIPAIS
all: $(EXECUTABLE)

# Gera o executável; garante que 'bin' exista
$(EXECUTABLE): $(OBJECTS) | $(BIN)
	$(CXX) $(CXXFLAGS) -I$(INCLUDE) $^ -o $@

# Regra para compilar cada .cpp em .o; garante que 'obj' exista
$(OBJ)/%.o: $(SRC)/%.cpp | $(OBJ)
	$(CXX) $(CXXFLAGS) -I$(INCLUDE) -c $< -o $@

# Cria o diretório obj se não existir
$(OBJ):
	mkdir -p $(OBJ)

# Cria o diretório bin se não existir
$(BIN):
	mkdir -p $(BIN)

# Atalho para rodar
run: all
	./$(EXECUTABLE)

# Limpeza
clean:
	rm -rf $(OBJ)/*.o $(EXECUTABLE)
