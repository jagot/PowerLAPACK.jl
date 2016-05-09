# PowerLAPACK

[![Build Status](https://travis-ci.org/jagot/PowerLAPACK.jl.svg?branch=master)](https://travis-ci.org/jagot/PowerLAPACK.jl)

Package used for development towards implementing [JuliaLang/julia#16263](https://github.com/JuliaLang/julia/issues/16263).

[Example](/test/test_stegr.jl) for eigendecomposition of symmetric tridiagonal matrix:
```
2000×2000 symmetric tridiagonal matrix, 100 iterations
eigfact:
 27.124645 seconds (5.00 k allocations: 6.013 GB, 6.93% gc time)
stegr! w/ prealloc'd work, passed as splat array:
 24.967008 seconds (700 allocations: 15.625 KB)
stegr! w/ prealloc'd work, passed separately:
 24.683399 seconds
```
For this case, there does not seem to be a big difference, but comparing with the same test [run on the Travis CI server](https://travis-ci.org/jagot/PowerLAPACK.jl/jobs/128833162), the situation is very different:
```
2000×2000 symmetric tridiagonal matrix, 100 iterations
eigfact:
184.169429 seconds (1.99 G allocations: 41.651 GB, 4.88% gc time)
stegr! w/ prealloc'd work, passed as splat array:
 31.179624 seconds (1.50 k allocations: 28.125 KB)
stegr! w/ prealloc'd work, passed separately:
 31.165003 seconds (800 allocations: 12.500 KB)
```
Not sure about this huge discrepancy.

Pull requests welcome!

Routines that need splitting into allocation + execution = driver (those that appear more than once have more than one implementation):

- [ ] `gbtrf!`
- [ ] `gebal!`
- [ ] `gebrd!`
- [ ] `gelqf!`
- [ ] `geqlf!`
- [ ] `geqp3!`
- [ ] `geqrt!`
- [ ] `geqrf!`
- [ ] `gerqf!`
- [ ] `getrf!`
- [ ] `geqp3!`
- [ ] `geqp3!`
- [ ] `tzrzf!`
- [ ] `ormrz!`
- [ ] `gels!`
- [ ] `gesv!`
- [ ] `getri!`
- [ ] `gesvx!`
- [ ] `gesvx!`
- [ ] `gelsd!`
- [ ] `gelsy!`
- [ ] `gelsd!`
- [ ] `gelsy!`
- [ ] `gglse!`
- [ ] `geev!`
- [ ] `gesdd!`
- [ ] `gesvd!`
- [ ] `ggsvd!`
- [ ] `ggsvd3!`
- [ ] `ggsvd3!`
- [ ] `geevx!`
- [ ] `ggev!`
- [ ] `geevx!`
- [ ] `ggev!`
- [ ] `laic1!` Not sure if necessary
- [ ] `laic1!` Not sure if necessary
- [ ] `gttrf!`
- [ ] `orglq!`
- [ ] `orgqr!`
- [ ] `orgql!`
- [ ] `orgrq!`
- [ ] `ormlq!`
- [ ] `ormqr!`
- [ ] `ormql!`
- [ ] `ormrq!`
- [ ] `gemqrt!`
- [ ] `potrf!`
- [ ] `pstrf!`
- [ ] `pttrf!`
- [ ] `trcon!`
- [ ] `trevc!`
- [ ] `trrfs!`
- [ ] `trcon!`
- [ ] `trevc!`
- [ ] `trrfs!`
- [x] `stev!`
- [ ] `stebz!`
- [x] `stegr!`
- [ ] `stein!`
- [ ] `syconv!`
- [ ] `sysv!`
- [ ] `sytrf!`
- [ ] `sytri!`
- [ ] `sysv_rook!`
- [ ] `sytrf_rook!`
- [ ] `sytri_rook!`
- [ ] `syconv!`
- [ ] `hesv!`
- [ ] `hetrf!`
- [ ] `hetri!`
- [ ] `hesv_rook!`
- [ ] `hetrf_rook!`
- [ ] `hetri_rook!`
- [ ] `sysv!`
- [ ] `sytrf!`
- [ ] `sytri!`
- [ ] `sysv_rook!`
- [ ] `sytrf_rook!`
- [ ] `sytri_rook!`
- [ ] `syev!`
- [ ] `syevr!`
- [ ] `sygvd!`
- [ ] `syev!`
- [ ] `syevr!`
- [ ] `sygvd!`
- [ ] `bdsqr!`
- [ ] `bdsdc!`
- [ ] `gecon!`
- [ ] `gecon!`
- [ ] `gehrd!`
- [ ] `orghr!`
- [ ] `ormhr!`
- [ ] `gees!`
- [ ] `gges!`
- [ ] `gees!`
- [ ] `gges!`
- [ ] `trexc!`
- [ ] `trsen!`
- [ ] `tgsen!`
- [ ] `trsen!`
- [ ] `tgsen!`
- [ ] `trsyl!`
