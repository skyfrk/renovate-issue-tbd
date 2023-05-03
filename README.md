# renovate-nuget-discussion-21951

Minimal reproduction repository for <https://github.com/renovatebot/renovate/discussions/21951>.

## Expected behavior

`packages.lock.json` is updated to

```json
{
  "version": 1,
  "dependencies": {
    "net7.0": {
      "MediatR": {
        "type": "Direct",
        "requested": "[12.0.1, )",
        "resolved": "12.0.1",
        "contentHash": "vfxplMielft+g5jxGO31xjjQpI6yqe4r2YGt0Q8x23phwbpJNmUQGY+cCNNFMKKViXRM67ajUlAiwirMeuJWTQ==",
        "dependencies": {
          "MediatR.Contracts": "[2.0.1, 3.0.0)",
          "Microsoft.Extensions.DependencyInjection.Abstractions": "6.0.0"
        }
      },
      "MediatR.Contracts": {
        "type": "Transitive",
        "resolved": "2.0.1",
        "contentHash": "FYv95bNT4UwcNA+G/J1oX5OpRiSUxteXaUt2BJbRSdRNiIUNbggJF69wy6mnk2wYToaanpdXZdCwVylt96MpwQ=="
      },
      "Microsoft.Extensions.DependencyInjection.Abstractions": {
        "type": "Transitive",
        "resolved": "6.0.0",
        "contentHash": "xlzi2IYREJH3/m6+lUrQlujzX8wDitm4QGnUu6kUXTQAWPuZY8i+ticFJbzfqaetLA6KR/rO6Ew/HuYD+bxifg=="
      }
    }
  }
}
```

when RenovateBot tries to update the `PackageReference` to `MediatR` to version `12.0.1` in `Directory.Build.props`.

## Actual behavior

`packages.lock.json` is not updated.
