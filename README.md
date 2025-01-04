# fake-ip-filter
An exception for domains that are incompatible with [fake IP](https://www.rfc-editor.org/rfc/rfc3089).

## License

[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)

## Usage

1. Add the following subscription to the mihomo/clash-meta configuration file.

    ```
    rule-providers:
      fake-ip-filter:
        type: http
        behavior: domain
        url: "https://raw.githubusercontent.com/5l2/fake-ip-filter/master/fake_ip_filter_subscription.payload"
        interval: 600
    ```

2. Modify the dns module configuration in the mihomo/clash-meta configuration file as follows.

    ```
    dns:
      fake-ip-filter:
        - rule-set:fakeip-filter
      fake-ip-filter-mode: blacklist
    ```
