# 자료구조 11강 그래프

## 그래프의 정의 
- 유관한 사물 또는 개념끼리 서로 연결한 것
- 네트워크
- 연결리스트나 트리도 그래프에 해당
- 정점 vertex 과 간선 edge의 유한집합

## 그래프 종류
- 간선의 방향성 유무 : 방향그래프 | 무방향 그래프
- 간선의 중복 여부 : 단순 그래프 | 다중 그래프
- 완전 그래프 : 간선을 최대한으로 가진 그래프 `n(n-1)/2` -> 무방향그래프, `n(n-1)` -> 방향그래프
- 부분 그래프 : 다른 그래프의 일부 간선과 정접으로 구성되는 그래프 

## 그래프 개념
- 경로의 길이 : 경로를 구성하는 간선의 수
- 단순 경로 : 모두 상이한 간선들로 구성된 경로 
- 사이클 : 첫 번 째 정점과 마지막 정점이 동일한 단순 경로
- DAG : 방향 그래프에서 사이클이 없는 그래프 
- 연결그래프 | 단절그래프
- 차수 
  - 무방향 그래프에서 그 정접에 부속된 간선의 수
  - 방향그래프의 차수: 진입차수 | 진출차수

## 인접행렬 Adjacency Matrix
- 배열을 이용한 그래프 표현
- 정점 i와 j 사이에 간선이 존재하는 경우 `mat[i][j] = 1`
- 가중치 그래프는 가중치 값을 대신 넣음
- 무방향그래프일 시 행렬의 상위 삼각이나 하위 삼각만 저장한다면 거의 반 정도의 공간을 절약
- 방향그래프일 시 행i의 합은 정점i의 진출 차수, 열 i의 합은 정점 i의 진입 차수

## 인접리스트 Adjacency List
- 무방향그래프
  - 정점의 인접리스트에 있는 노드 수 계산 -> 정점의 차수
  - 전체 간선 수 계산에 걸리는 시간 O(n+e)
- 방향그래프 
  - 진출 차수 : 인접리스트의 노드수
  - 진입 차수 : 역인접리스트 별도로 유지 
 
## 인접다중리스트 Adjacency Multilist
간선에 부속된 두 정점 각각에 대한 인접 리스트를 다중 리스트로 유지하여, 하나의 간선을 두 개의 리스트가 공유하는 리스트

## 그래프순회 Graph Traversal
주어진 어떤 정점을 출발하여 체계적으로 그래프의 모든 정점들을 순회하는 것 
- 깊이우선탐색 depth first search 스택 이용
- 너비우선탐색 breath first search 큐 이용

## 신장트리 Spanning Tree
- 그래프 G의 모든 정점을 포함하는 트리 형태의 부분
- 하나의 그래프에 대해 여러 개의 신장 트리가 존재할 수 있음

### 신장트리 종류 
- 깊이우선 신장트리
- 너비우선 신장트리

#### 최소 연결 부분그래프 Minimal Connected Subgraph
- V(G') = V(G)
- E(G') <= E(G)
- G'는 연결 그래프
- G'는 최소의 간선수를 포함
- 신장 트리는 최소 연결 부분 그래프임
- 도시 간 네트워커 설계에서 최소 링크 수를 구하는 데 사용