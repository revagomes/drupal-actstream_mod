# Activity Stream Moderation

[![CI](https://github.com/revagomes/drupal-actstream_mod/actions/workflows/ci.yml/badge.svg?branch=2.0.x)](https://github.com/revagomes/drupal-actstream_mod/actions/workflows/ci.yml)
[![Drupal 10.3+/11](https://img.shields.io/badge/Drupal-10.3%2B%20%7C%2011-0678BE.svg)](https://www.drupal.org/project/activitystream_mod)
[![License: GPL-2.0-or-later](https://img.shields.io/badge/License-GPL--2.0--or--later-blue.svg)](https://www.gnu.org/licenses/old-licenses/gpl-2.0.html)

**Activity Stream Moderation** is a sub-module for [Activity Stream (actstream)](https://www.drupal.org/project/actstream). It adds a moderation workflow to `actstream_item` entities so that incoming items from external services must be approved before they are published.

---

## Requirements

- PHP 8.1+
- Drupal 10.3 or 11
- [actstream](https://www.drupal.org/project/actstream) 2.0+

---

## Installation

```bash
composer require drupal/actstream_mod
drush en actstream_mod -y
```

On install the module adds an `actstream_mod_moderated` boolean field to the `actstream_item` entity type and sets all new items to unpublished by default.

---

## How it works

| Behaviour | Details |
|-----------|---------|
| New items | Always saved as unpublished (`status = 0`) and unmoderated |
| Edit form | Approve and Disapprove buttons replace the default Save button for users with the moderation permission |
| Approve | Publishes the item and marks it as moderated |
| Disapprove | Unpublishes the item and marks it as moderated |

---

## Permissions

Grant the **Moderate Activity Stream items** permission to the roles responsible for content review.

---

## Development

```bash
composer install
vendor/bin/phpcs --standard=Drupal,DrupalPractice actstream_mod.module actstream_mod.install
php -l actstream_mod.module && php -l actstream_mod.install
```

---

## Project links

- Drupal.org project page: <https://www.drupal.org/project/activitystream_mod>
- Issue queue: <https://www.drupal.org/project/issues/activitystream_mod>
- GitHub mirror: <https://github.com/revagomes/drupal-actstream_mod>

---

## License

GPL-2.0-or-later. See [LICENSE](LICENSE) for the full text.
