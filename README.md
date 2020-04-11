# OpenGL - Tutorial 
To repozytorium zawiera cały kod projektu z poszczególnych odcinków naszej serii

[OpenGL Tutorial](https://www.youtube.com/playlist?list=PLO8RnRe_0dcXw-jdkUUtVo6ZATArEwfIa) to seria odpowiadająca na najbardziej nurtujące nas pytania związane z programowaniem grafiki przy użyciu biblioteki OpenGL oraz języka C++

Cały [mój kanał](https://www.youtube.com/user/LeftarCode) stara się wprowadzić was w świat tworzenia własnych silników graficznych krok po kroku przez podstawowe zgadnienia związane z bibliotekami graficznych na samej architekturze i ciekawych rozwiązanach kończąc


# Zależności
### Biblioteki
 - [**Assimp**](https://www.assimp.org/) - wykorzystywany do ładowania modeli 3D
 - [**GLEW**](http://glew.sourceforge.net/) - biblioteka agregująca wszystkie rozszerzenia i funkcje OpenGL'a
 - [**GLFW**](https://www.glfw.org/) - służy do tworzenia okienek, obsługi zdarzeń wejścia/wyjścia
 - [**GLM**](https://glm.g-truc.net/0.9.9/index.html) - bardzo prosta, ale niesamowicie potężna biblioteka do obliczeń matematycznych
 - [**STBImage**](https://github.com/nothings/stb) - prosta biblioteka do ładowania tekstur
### Narzędzia
 - **Visual Studio 2019** - wszystkie projekty w tym repozytorium zostały stworzone przy użyciu tego IDE. W przyszłości na pewno pojawi `CMakeLists.txt` żeby każdy z was mógł zbudować projekt pod środowisko z którego korzysta
 - **CMake** - do zbudowania projektów oraz biblioteki **Assimp**
# Jak używać
 - `cmake . -B build` - tworzy projekt z całego kodu, dla prostoty użytkownika zalecam wykorzystanie wersji z [GUI](https://cmake.org/download/)
