# Unreal
## Enhanced Input
- IA_Move를 IMC에 바인딩 할때 강의와 자료에서 WASD키에 Swizzle, Negate거는 방식이 달라서 검색해보았다. (d:None or d:Swizzle)
- 결론은 어떤축을 기준으로 하느냐인데 키보드의 기본 축을 X축으로 볼건지 Y축으로 볼건지에 따라 다른거였다.

### IA_Move
- 보통 Axis2D: FVector2D(X,Y)

### 키보드는 1D
- 1차원 값으로 누르면 1.0 때면 0.0
- 우리는 WASD를 사용하기 위해 Modifiers를 이용해 2차원값으로 값을 수정해줘야함

### Swizzle, Negate
- Swizzle은 입력이 (val, 0)이면 (0, val)로 축을 재배치 시킴
- Negate는 (val, 0)이면 (-val, 0)으로 부호 반전

### 결론
- (기본 입력 Y축)
W: None
S: Negate
A: Negate + Swizzle
D: Swizzle

- (기본 입력 X축)
W: Swizzle
S: Swizzle + Negate
A: Negate
D: None

---