# UnmaskingPhishers

### Cerrtificate Based features

| Feature                    | Type  | Description                                                                    |
|----------------------------|-------|--------------------------------------------------------------------------------|
| validation_level          | int   | Validation level of the certificate                                            |
| apple_ever_valid         | bool  | If the certificate has ever been considered valid by the Apple root store |
| nss_ever_valid           | bool  | If the certificate has ever been considered valid by the Mozilla NSS root store    |
| microsoft_ever_valid     | bool  | If the certificate has ever been considered valid  by the Microsoft root store  |
| subject_has_country      | bool  | If the subject has anything in the country field                               |
| subject_has_province     | bool  | If the subject has anything in the province field                              |
| subject_has_locality     | bool  | If the subject has anything in the locality field                              |
| subject_has_common_name | bool  | If the subject has anything in the common name field     |
| subject_only_cn          | bool  | If the subject only has something in the common name field and all other subject fields are empty    |
| subject_len               | int   | Length of the subject                                                          |
| length_seconds            | int   | Length of the validity period in seconds                                       |
| ocsp_urls                 | bool  | If the certificate has an OCSP (Online Certificate Status Protocol) URL |
| crl_dist_point_present  | bool  | If the certificate has an CDP (CRL distribution  point) URL    |
| num_san_dns_names       | int   | Number of SANs in the DNS names field                                          |
| pub_key_algorithm        | cat   | The public key algorithm                                                       |
| version                    | int   | Version of the certificate                                                     |
| signature_algorithm_name | cat   | The signature algorithm name                                                   |
| len_serial_number        | int   | Length of the serial number                                                    |
| len_issuer_dn            | int   | Length of the issuer                                                           |
| issuer_has_common_name  | bool  | If the issuer has a common name                                                |
| subject_is_empty         | bool  | If the subject is empty                                                        |
| lcs_sans                  | int   | The longest common subsequence of all the SANs                                 |
| lcs_sans_normed          | float | The longest common subsequence of all the SANs, normalized    |
| authority_info_access    | bool  | If the certificate has authority information access present |
| certificate_policies      | bool  | If the certificate has certificate policies present                            |
| basic_constraints         | bool  | If the certificate has basic constraints present                               |
| key_usage_value          | int   | The key usage                                                                  |
| authority_key_id         | bool  | If the certificate has authority key id present                                |

### SAN based features


| Feature                           | Type  | Description                                                          |
|-----------------------------------|-------|----------------------------------------------------------------------|
| mean_san_domain_len            | float | Average length of the domains in the SAN                             |
| san_sus_keyword                 | float | Number of domains in the SAN that have a suspicious keyword divided by the number of SANs   |
| san_sus_tld                     | float | Number of domains in the SAN that have a suspicious TLD divided by the number of SANs, suspicious TLDs from sources mention in paper  |
| san_shannon_entropy             | float | Average Shannon entropy for the SANs                                 |
| san_num_dashes                  | float | Average number of "-" in the SAN domains                             |
| san_num_tokens                  | float | Average number of tokens in the SAN domains                          |
| san_num_parts                   | float | Average number of parts in the SAN domains                           |
| san_token_is_tld               | float | Number of domains in the SAN that have a TLD as a token divided by the number of SANs |
| san_frac_special_char          | float | Fraction of special characters on average in the SANs |
| san_is_international            | float | Number of domains in the SAN that are international domains divided by the number of SANs    |
| san_frac_vowels                 | float | Fraction of vowels on average in the SANs                            |
| san_frac_digits                 | float | Fraction of digits on average in the SANs                            |
| san_has_digit_only_subdomain  | float | Number of domains in the SAN that have a digit only subdomain divided by the number of SANs   |
| san_mean_len_subdomains        | float | Average subdomain length in the SANs                                 |
| san_has_single_char_subdomain | float | Number of domains in the SAN that have single character subdomain divided by the number of SANs   |
| san_char_diversity              | float | verage char diversity in the SANs                                   |
| san_alphabet_size               | float | Average alphabet size in the SANs                                    |

### Domain based features

| Feature                      | Type  | Description                                                               |
|------------------------------|-------|---------------------------------------------------------------------------|
| domain_len                  | int   | Length of the domain including "."                                        |
| sus_keyword                 | bool  | If the domain contain a suspicious keyword                                |
| sus_tld                     | bool  | If the domain has a suspicious TLD, suspicious TLDs from from sources mention in paper |
| shannon_entropy             | float | Shannon Entropy of the domain                                             |
| num_dashes                  | int   | Number of "-" in the domain                                               |
| num_tokens                  | int   | Number of tokens. A token is a part of the domain between "-" or "."    |
| num_parts                   | int   | Number of parts. A part is between two "."                                |
| token_is_tld               | bool  | If a part of the domain is a TLD                                          |
| frac_special_char          | float | Fraction of the domain that is a special character                        |
| is_international            | bool  | If the domain is International Domain Name, that is it contains any international characters    |
| frac_vowels                 | float | Fraction of the domain that are vowels                                    |
| frac_digits                 | float | Fraction of the domain that are digits                                    |
| has_digit_only_subdomain  | bool  | If the domain contains a subdomain that is only digits    |
| mean_len_subdomains        | float | Mean of the lengths of the subdomains of the domain      |
| has_single_char_subdomain | bool  | If the domain has single character subdomains                             |
| char_diversity              | float | Fraction of unique characters in the domain to the total number of characters   |
| alphabet_size               | int   | Number of unique characters in the domain                                 |
| is_wildcard_match          | bool  | If the certificate matched to the domain through a wildcard SAN      |
| has_wildcard_san           | bool  | If the certificate contains a wildcard SAN                                |

