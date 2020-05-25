# int 형으로 ip 저장

| Name                                                         | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [`ANY_VALUE()`](https://dev.mysql.com/doc/refman/5.7/en/miscellaneous-functions.html#function_any-value) | Suppress ONLY_FULL_GROUP_BY value rejection                  |
| [`DEFAULT()`](https://dev.mysql.com/doc/refman/5.7/en/miscellaneous-functions.html#function_default) | Return the default value for a table column                  |
| [`INET_ATON()`](https://dev.mysql.com/doc/refman/5.7/en/miscellaneous-functions.html#function_inet-aton) | Return the numeric value of an IP address                    |
| [`INET_NTOA()`](https://dev.mysql.com/doc/refman/5.7/en/miscellaneous-functions.html#function_inet-ntoa) | Return the IP address from a numeric value                   |
| [`INET6_ATON()`](https://dev.mysql.com/doc/refman/5.7/en/miscellaneous-functions.html#function_inet6-aton) | Return the numeric value of an IPv6 address                  |
| [`INET6_NTOA()`](https://dev.mysql.com/doc/refman/5.7/en/miscellaneous-functions.html#function_inet6-ntoa) | Return the IPv6 address from a numeric value                 |
| [`IS_IPV4()`](https://dev.mysql.com/doc/refman/5.7/en/miscellaneous-functions.html#function_is-ipv4) | Whether argument is an IPv4 address                          |
| [`IS_IPV4_COMPAT()`](https://dev.mysql.com/doc/refman/5.7/en/miscellaneous-functions.html#function_is-ipv4-compat) | Whether argument is an IPv4-compatible address               |
| [`IS_IPV4_MAPPED()`](https://dev.mysql.com/doc/refman/5.7/en/miscellaneous-functions.html#function_is-ipv4-mapped) | Whether argument is an IPv4-mapped address                   |
| [`IS_IPV6()`](https://dev.mysql.com/doc/refman/5.7/en/miscellaneous-functions.html#function_is-ipv6) | Whether argument is an IPv6 address                          |
| [`MASTER_POS_WAIT()`](https://dev.mysql.com/doc/refman/5.7/en/miscellaneous-functions.html#function_master-pos-wait) | Block until the slave has read and applied all updates up to the specified position |
| [`NAME_CONST()`](https://dev.mysql.com/doc/refman/5.7/en/miscellaneous-functions.html#function_name-const) | Cause the column to have the given name                      |
| [`SLEEP()`](https://dev.mysql.com/doc/refman/5.7/en/miscellaneous-functions.html#function_sleep) | Sleep for a number of seconds                                |
| [`UUID()`](https://dev.mysql.com/doc/refman/5.7/en/miscellaneous-functions.html#function_uuid) | Return a Universal Unique Identifier (UUID)                  |
| [`UUID_SHORT()`](https://dev.mysql.com/doc/refman/5.7/en/miscellaneous-functions.html#function_uuid-short) | Return an integer-valued universal identifier                |
| [`VALUES()`](https://dev.mysql.com/doc/refman/5.7/en/miscellaneous-functions.html#function_values) | Define the values to be used during an INSERT                |

MySQL 5.7 기준 제공하는 함수 리스트이다. 
오늘은 IP4를 MySLQ에 저장하는 방법을 알아보자.



## INET_ATON

```mysql
mysql> SELECT INET_ATON('10.0.5.9');
        -> 167773449
```



변환하는 방법

10×2563 + 0×2562 + 5×256 + 9.



## INET_NTOA

```mysql
mysql> SELECT INET_NTOA(167773449);
        -> '10.0.5.9'
```





## 참고

https://dev.mysql.com/doc/refman/5.7/en/miscellaneous-functions.html