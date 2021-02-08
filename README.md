# temp-chart

## 구조

- `charts` 디렉터리 = `charts_dir: charts`. 차트 디렉터리를를 감싸는 디렉터리다. 
  - `example` 차트 디렉터리: `charts` 디렉터리 바로 밑에 `Charts.yaml`을 둘 수 없다.
    - `example`가 `charts` 디렉터리가 아닌 최상위 디렉터리에 있다면 `charts_dir: .`로 설정해야 하는데, 그렇게 되면 다른 파일들도 `git diff` 명령에 포함된다. → [code](https://github.com/helm/chart-releaser-action/blob/c3d308d0c55d41f25565d9db5534da82dd8b07d7/cr.sh#L226)
    - `Chart.yaml` 파일: 이 파일은 `<project_dir>/<charts_dir>/<chart_name>/Chart.yaml` 경로에 정확하게 있어야 한다.

``` bash
.
├── README.md
└── charts
    └── example
        ├── Chart.yaml
        ├── templates
        │   └── configmap.yaml
        └── values.yaml
```

