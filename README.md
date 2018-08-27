# Composer-command
## Composer là gì?

Composer là một công cụ quản lí các dependency. Nó cho phép bạn khai báo các thư viện mà project phụ thuộc vào, đồng thời quản lý (install/update) chúng cho bạn.

## Global Options[#](#global-options)

*   **--verbose (-v):** Tăng sự rõ ràng cho các message.
*   **--help (-h):** Hiển thị thông tin trợ giúp. 
*   **--quiet (-q):** Không trả về bất cứ message nào.
*   **--no-interaction (-n):** Không hỏi bất cứ câu hỏi tương tác nào.
*   **--no-plugins:** Vô hiệu hóa các plugin.
*   **--working-dir (-d):** Nếu chi tiết, sử dụng thư mục được chỉ định làm thư mục làm việc.
*   **--profile:** Hiển thị thời gian và thông tin bộ nhớ sử dụng.
*   **--ansi:** Bắt buộc trả về ANSI.
*   **--no-ansi:** Vô hiệu hóa trả về ANSI.
*   **--version (-V):** Hiển thị phiên bản của ứng dụng này.

## Process Exit Codes[#](#process-exit-codes)

*   **0:** OK
*   **1:** Generic/unknown error code
*   **2:** Dependency solving error code

## init[#](#init)

Lệnh `init` giúp tạo file composer.json dễ dàng hơn.

Khi bạn chạy lệnh trên, nó sẽ yêu cầu bạn điền vào các trường, trong khi sử dụng những mặc định thông minh.

    php composer.phar init

### Options

*   **--name:** Tên của package.
*   **--description:** Miên tả về package.
*   **--author:** Tên tác giả của package.
*   **--type:** Loại package.
*   **--homepage:** Trang chủ của package.
*   **--require:** Package require phiên bản hạn chế. Nên có dạng: `foo/bar:1.0.0`.
*   **--require-dev:** Require cho bản development, xem **--require**.
*   **--stability (-s):** Giá trị cho trường `minimum-stability`.
*   **--license (-l):** Giấy phép của package.
*   **--repository:** Cung cấp một (hoặc hơn) repo tùy chỉnh. Chúng sẽ được lưu trữ trong composer.json được tạo mới, và được sử dụng cho auto-completion khi thông báo danh sách các require. Mỗi repo có thể là một HTTP URL trỏ đến một repo `composer` hoặc một chuỗi JSON tương tự với những gì [repositories](04-schema.md#repositories) key chấp nhận.

## install / i[#](#install-i)

Lệnh `install` đọc file `composer.json` trong thư mục hiện tại, xác định các dependency, và install chúng vào trong `vendor`. 

    php composer.phar install

Nếu có file `composer.lock` trong thư mục hiện tại, nó sẽ sử dụng chính xác các phiên bản từ đó thay vì xác định lại chúng. Điều này chắc chắn rằng bất cứ ai sử dụng thư viện đều sẽ nhận được cùng một phiên bản của các dependency.

Nếu không có file `composer.lock`, Composer sẽ tạo nó sau khi xác định dependency.

### Options

*   **--prefer-source:** 
*   **--prefer-dist:** 
*   **--dry-run:** 
*   **--dev:** 
*   **--no-dev:** 
*   **--no-autoloader:**
*   **--no-scripts:** 
*   **--no-progress:** 
*   **--no-suggest:** 
*   **--optimize-autoloader (-o):** 
*   **--classmap-authoritative (-a):** 
*   **--apcu-autoloader:**
*   **--ignore-platform-reqs:** 

## update / u[#](#update-u)

Để sử dụng phiên bản dependency mới nhất và cập nhật file `composer.lock`, ta nên sử dụng lệnh `update`. 

    php composer.phar update

Nếu không muốn update tất cả, có thể  liệt kê chi tiết như sau:

    php composer.phar update vendor/package vendor/package2

Để update một loạt package cùng lúc:

    php composer.phar update vendor/*

### Options

*   **--prefer-source:** 
*   **--prefer-dist:** 
*   **--dry-run:** 
*   **--dev:** 
*   **--no-dev:** 
*   **--lock:** 
*   **--no-autoloader:** 
*   **--no-scripts:** 
*   **--no-progress:** 
*   **--no-suggest:** 
*   **--with-dependencies:** 
*   **--with-all-dependencies:** 
*   **--optimize-autoloader (-o):** 
*   **--classmap-authoritative (-a):**
*   **--apcu-autoloader:** 
*   **--ignore-platform-reqs:** 
*   **--prefer-stable:**
*   **--prefer-lowest:**
*   **--interactive:** 
*   **--root-reqs:**

## require[#](#require)

Lệnh `require` thêm các package mới vào file `composer.json` trong thư mục hiện tại. Nếu file không tồn tại nó sẽ được tạo mới.

    php composer.phar require

Sau khi thêm/thay đổi các require, các bản require đã được điều chỉnh sẽ được cài đặt hoặc cập nhật.

### Options

*   **--dev:** 
*   **--prefer-source:** 
*   **--prefer-dist:** 
*   **--no-progress:** 
*   **--no-suggest:** 
*   **--no-update:** 
*   **--no-scripts:**
*   **--update-no-dev:** 
*   **--update-with-dependencies:** 
*   **--update-with-all-dependencies:** 
*   **--ignore-platform-reqs:** 
*   **--prefer-stable:** 
*   **--prefer-lowest:** 
*   **--sort-packages:**
*   **--optimize-autoloader (-o):** 
*   **--classmap-authoritative (-a):** 
*   **--apcu-autoloader:** 

## remove[#](#remove)

Lệnh `remove` loại bỏ các package khỏi file `composer.json` từ thư mục hiện tại.

    php composer.phar remove vendor/package vendor/package2

Sau khi loại bỏ các bản require, các require đã được điều chỉnh sẽ bị gỡ bỏ.

### Options

*   **--dev:**
*   **--no-progress:** 
*   **--no-update:** 
*   **--no-scripts:** 
*   **--update-no-dev:**
*   **--update-with-dependencies:** 
*   **--ignore-platform-reqs:** 
*   **--optimize-autoloader (-o):** 
*   **--classmap-authoritative (-a):** 
*   **--apcu-autoloader:** 

## check-platform-reqs[#](#check-platform-reqs)

Lệnh check-platform-reqs kiểm tra phiên bản PHP và phiên bản của các extensions có ăn khớp với các require của plattform về các package đã được cài đặt hay không. Lệnh này có thể được sử dụng để xác thực rằng một production server đã có tất cả các extension cần thiết để chạy project sau khi cài đặt chẳng hạn.

## global[#](#global)

Lệnh global cho phép bạn chạy các lệnh như `install`, `remove`, `require` or `update` như là chạy chúng trong thư mục [COMPOSER_HOME](#composer-home).

## search[#](#search)

Lệnh search cho phép bạn tìm kiếm trong các repo package của project hiện tại. Thông thường nó sẽ là packagist. Bạn chỉ cần đơn giản pass các tham số mà bạn muốn:

    php composer.phar search monolog

Bạn cũng có thể tìm kiếm bởi nhiều mục hơn bằng cách pass qua nhiều tham số cùng lúc.

### Options

*   **--only-name (-N):** 
*   **--type (-t):** 

## show[#](#show)

Liệt kê danh sách tất các các package khả dụng, bạn có thể dùng lệnh `show`.

    php composer.phar show

### Options

*   **--all :** 
*   **--installed (-i):**
*   **--platform (-p):** 
*   **--available (-a):** 
*   **--self (-s):**
*   **--name-only (-N):** 
*   **--path (-P):** 
*   **--tree (-t):** 
*   **--latest (-l):** 
*   **--outdated (-o):**
*   **--minor-only (-m):** 
*   **--direct (-D):**
*   **--strict:** 
*   **--format (-f):** 

## outdated[#](#outdated)

Lệnh `outdated` hiển thị một danh sách các package đã được cài đặt mà có các bản cập nhật khả dụng, bao gồm cả các phiên bản hiện tại và mới nhất của chúng. Đây chỉ là cách gọi khác của `composer show -lo`.

Kết quả trả về có thể có các màu với ý nghĩa tương ứng:

*   **green (=)**: Dependency là phiên bản mới nhất.
*   **yellow (~)**: Dependency có phiên bản mới hơn bao gồm khả năng tương thích ngược vì vậy hãy nâng cấp ngay khi bạn có thể nhưng nó cũng có thể ảnh hưởng đến công việc.
*   **red (!)**: Dependency có phiên bản mới tương thích và bạn nên nâng cấp nó ngay khi có thể.

### Options

*   **--all (-a):** 
*   **--direct (-D):** 
*   **--strict:** 
*   **--minor-only (-m):** 
*   **--format (-f):** 

## browse / home[#](#browse-home)

Lệnh `browse` (cách gọi khác của `home`) mở ra một repo URL của package trong trình duyệt của bạn.

### Options

*   **--homepage (-H):**
*   **--show (-s):**

## suggests[#](#suggests)

Liệt kê tất cả package được đề nghị bởi tập hợp các package đã được cài đặt hiện tại. 

### Options

*   **--by-package:** 
*   **--by-suggestion:** 
*   **--no-dev:** 

## depends (why)[#](#depends-why-)

Lệnh`depends` cho bạn biết các package khác nào phụ thuộc vào một package định trước. 

    php composer.phar depends doctrine/lexer
     doctrine/annotations v1.2.7 requires doctrine/lexer (1.*)
     doctrine/common      v2.6.1 requires doctrine/lexer (1.*)

### Options

*   **--recursive (-r):** 
*   **--tree (-t):** 

## prohibits (why-not)[#](#prohibits-why-not-)

Lệnh `prohibits` cho bạn biết các package nào đang block một package cho trước khỏi việc cài đặt. Chỉ định chính xác phiên bản hạn chế để xác thực liệu việc nâng câp có thể được báo trước trong project của bạn, và nếu không thì tại sao. Xem ví dụ sau:

    php composer.phar prohibits symfony/symfony 3.1
     laravel/framework v5.2.16 requires symfony/var-dumper (2.8.*|3.0.*)

Ghi nhớ rằng bạn cũng có thể chỉ định các bản require platform, chẳng hạn như kiểm tra xem liệu bạn có thể nâng cấp server của mình lên PHP 8.0 hay không:

    php composer.phar prohibits php:8
     doctrine/cache        v1.6.0 requires php (~5.5|~7.0)
     doctrine/common       v2.6.1 requires php (~5.5|~7.0)
     doctrine/instantiator 1.0.5  requires php (>=5.3,<8.0-DEV)

### Options

*   **--recursive (-r):** 
*   **--tree (-t):** 

## validate[#](#validate)

Bạn nên nhớ luôn chạy lệnh `validate` trước khi commit file `composer.json`, và trước khi gắn thẻ một bản phát hành. Nó sẽ kiểm tra xem `composer.json` có hợp lệ hay không.

    php composer.phar validate

### Options

*   **--no-check-all:** 
*   **--no-check-lock:** 
*   **--no-check-publish:** 
*   **--with-dependencies:** 
*   **--strict:** 

## status[#](#status)

Nếu bạn thường xuyên cần chỉnh sửa code của các dependency và chúng đã được cài đặt từ source, lệnh `status` cho phép bạn kiểm tra liệu bạn có có thay đổi cục bộ nào trong chúng hay không.

    php composer.phar status

Với option `--verbose` bạn sẽ có được thông tin rõ ràng hơn về các thay đổi:

    php composer.phar status -v

    You have changes in the following dependencies:
    vendor/seld/jsonlint:
        M README.mdown

## self-update (selfupdate)[#](#self-update-selfupdate-)

Để Composer tự cập nhật nó lên phiên bản mới nhất, chạy lệnh `self-update`. Nó sẽ thay thế `composer.phar` bằng phiên bản mới nhất.

    php composer.phar self-update


### Options

*   **--rollback (-r):** 
*   **--clean-backups:** 
*   **--no-progress:** 
*   **--update-keys:** 
*   **--stable:** 
*   **--preview:** 
*   **--snapshot:** 

## config[#](#config)

Lệnh `config` cho phép bạn điều chỉnh các thiệt lập cài đặt composer và các repo cả ở file `composer.json` cục bộ và file `config.json` toàn miền.

Thêm nữa là nó cho phép bạn điều chỉnh hầu hết các property trong file `composer.json` cục bộ.

    php composer.phar config --list

### Cách dùng[#](#usage)

`config [options] [setting-key] [setting-value1] ... [setting-valueN]`

`setting-key` là tên một option cấu hình và `setting-value1` giá trị cấu hình. Đối với các cài đặt mà có thể nhận một array các value (như `github-protocols`), thì sẽ có nhiều hơn một tham số setting-value được chấp nhận.

Bạn cũng có thể chỉnh sửa các giá trị của các property sau:

`description`, `homepage`, `keywords`, `license`, `minimum-stability`, `name`, `prefer-stable`, `type` and `version`.

Xem chương [Cấu hình](06-config.md).

### Options

*   **--global (-g):** 
*   **--editor (-e):** 
*   **--auth (-a):**
*   **--unset:** 
*   **--list (-l):** 
*   **--file="..." (-f):** 
*   **--absolute:** 

### Modifying Repositories[#](#modifying-repositories)

Để điều chỉnh mục cấu hình, lệnh `config` cũng hỗ  trợ tạo ra các thay đổi đối với các mục repo bằng cách sau:

    php composer.phar config repositories.foo vcs https://github.com/foo/bar

Nếu repo của bạn require nhiều option cấu hình hơn, bạn có thể truyền JSON đại diện của nó:

    php composer.phar config repositories.foo '{"type": "vcs", "url": "http://svn.example.org/my-project/", "trunk-path": "master"}'

### Modifying Extra Values[#](#modifying-extra-values)

    php composer.phar config extra.foo.bar value

## create-project[#](#create-project)

Bạn có thể sửu dụng Composer để tạo mới các project từ những package đã có. Điều này tương đương với việc thực hiện git clone/svn checkout theo sau bởi `composer install` của các vendor.

Có một số ứng dụng cho điều này:

1.  Bạn có thể triển khai các package ứng dụng.
2.  Bạn có thể check out bất cứ package nào và bắt đầu phát triển trên các bản khác chẳng hạn.
3.  Các project với nhiều dev có thể sử dụng tính năng này để khởi động ứng dụng ban đầu để phát triển. 

Để tạo mới project sử dụng Composer bạn có thể dùng lệnh `create-project`. Truyền cho nó một tên package, và thư mục để tạo mới project. Bạn cũng có thể cung cấp một phiên bản như là tham số thứ 3, nếu không thì phiên bản mới nhất sẽ được sử dụng.

Nếu thư mục không tồn tại, nó sẽ được tạo mới trong quá trình cài đặt.

    php composer.phar create-project doctrine/orm path 2.2.*

### Options

*   **--stability (-s):**
*   **--prefer-source:** 
*   **--prefer-dist:**
*   **--repository:**
*   **--dev:**
*   **--no-dev:** 
*   **--no-scripts:** 
*   **--no-progress:** 
*   **--no-secure-http:** 
*   **--keep-vcs:** 
*   **--remove-vcs:** 
*   **--no-install:** 
*   **--ignore-platform-reqs:** 

## dump-autoload (dumpautoload)[#](#dump-autoload-dumpautoload-)

Nếu bạn cần cập nhật autoloader vì do những class mới trong classmap package chẳng hạn, bạn có thể sử dụng `dump-autoload` để làm điều đò mà không cần phải chạy cài đặt hoặc cập nhật.

### Options

*   **--no-scripts:** 
*   **--optimize (-o):** 
*   **--classmap-authoritative (-a):** 
*   **--apcu:** 
*   **--no-dev:**

## clear-cache (clearcache)[#](#clear-cache-clearcache-)

Xóa tất cả nội dung khỏi các thư mục Composer cache.

## licenses[#](#licenses)

Liệt kê tên, phiên bản và giấy phép của mỗi package được cài đặt. Sử dụng `--format=json` để kết quả trả về dễ đọc hơn.

### Options

*   **--format:** 
*   **--no-dev:** 

## run-script[#](#run-script)

### Options

*   **--timeout:** 
*   **--dev:** 
*   **--no-dev:** 
*   **--list (-l):**

Để chạy [scripts](articles/scripts.md) thủ công, bạn có thể dùng lệnh này.

## exec[#](#exec)

Executes a vendored binary/script. You can execute any command and this will ensure that the Composer bin-dir is pushed on your PATH before the command runs.

### Options

*   **--list (-l):** List the available composer binaries.

## diagnose[#](#diagnose)

Nếu bạn nghĩ rằng bạn tìm thấy một bug, hoặc thứ gì đó hoạt động lạ lùng, bạn có thể muốn chạy lệnh `diagnose` để thực hiện các kiểm tra tự động cho nhiều vấn đề thường gặp.

    php composer.phar diagnose

## archive[#](#archive)

Lệnh này được dùng để tạo ra một zip/tar archive cho package cho trước ở phiên bản chỉ định. Nó có thể được sử dụng để lưu trữ toàn bộ project còn lại của bạn mà không bao gồm các file excluded/ignored.

    php composer.phar archive vendor/package 2.0.21 --format=zip

### Options

*   **--format (-f):** 
*   **--dir:** 
*   **--file:** 

## help[#](#help)

Để có thêm thông tin về lệnh đang sử dụng, hãy dùng `help`.

    php composer.phar help install

## Command-line completion[#](#command-line-completion)

Command-line hoàn chỉnh có trong hướng dẫn sau [on this page](https://github.com/bamarni/symfony-console-autocomplete).

## Environment variables[#](#environment-variables)

Bạn có thể thiết lập một số các biến môi trường mà ghi đè lên các cài đặt trước đó. Bất cứ khi nào có thể, hãy chỉ rõ những cài đặt này trong mục `config` của `composer.json`. Đáng để lưu ý rằng các biến env luôn chiếm vị trí quan trọng hơn các giá trị được chỉ định trong `composer.json`.

## require vs require --dev
Require sử dụng cho các giai đoạn staging và production trong khi require --dev sử dụng cho giai đoạn development và t

