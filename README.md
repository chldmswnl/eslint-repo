## ESLint 규칙 및 플러그인

### [@typescript-eslint/naming-convention](https://typescript-eslint.io/rules/naming-convention/#allowed-selectors-modifiers-and-types)

네이밍컨벤션을 위한 규칙

```cjs
"@typescript-eslint/naming-convention": [
      "error",
      {
        selector: "variable", // 변수
        format: ["camelCase", "PascalCase", "UPPER_CASE"],
      },
      {
        selector: "function", // 함수
        format: ["camelCase", "PascalCase"],
      },
      {
        // Group selector : class, enum, interface, typeAlias
        selector: "typeLike",
        format: ["PascalCase"],
      },
      {
        selector: "interface", // interface
        format: ["PascalCase"],
        prefix: ["I"],
      },
      {
        selector: "typeAlias", // type
        format: ["PascalCase"],
        custom: {
          regex: "^T[A-Z]",
          match: false,
        },
      },
    ],

```

- selector : 식별자 종류
- format : 식별자가 매칭되야 하는 포맷 (ex. camelCase, PascalCase, snake_case)
- prefix/suffix : 식별자의 prefix나 suffix를 지정
- custom: 식별자가 일치해야 하는 사용자 정의 정규식
  - regex: 정규식
  - match: true or false

### [eslint-plugin-no-relative-import-paths](https://github.com/MelvinVermeer/eslint-plugin-no-relative-import-paths)

절대경로를 위한 규칙

```cjs
{
  "rules": {
    // 같은 폴더인 경우를 제외하고 import 경로는 항상 절대 경로를 사용
    "no-relative-import-paths/no-relative-import-paths": [
      "warn",
      { "allowSameFolder": true, "rootDir": "src", "prefix": "@" }
    ]
  }
}
```

### [prettier-plugin-tailwindcss](https://github.com/tailwindlabs/prettier-plugin-tailwindcss)

Prettier Tailwind CSS 클래스 자동 정렬 플러그인

클래스 네임을 [권장 클래스 순서](https://tailwindcss.com/blog/automatic-class-sorting-with-prettier#how-classes-are-sorted)에 맞게 자동으로 정렬해주는 **프리티어** 플러그인

출처: https://techblog.woowahan.com/15903/#toc-6
