---
title: Planowanie globalnej książki adresowej i innych książek adresowych
description: W tym temacie opisano zagadnienia i decyzje, które należy uwzględnić w procesie planowania przed utworzeniem i skonfigurowaniem globalnej książki adresowej i wszelkich dodatkowych książek adresowych.
author: msftbrking
manager: AnnBe
ms.date: 01/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DirAddressBook, DirAddressBookTeam, DirParameters, DirPartyTable
audience: Application User
ms.reviewer: sericks
ms.custom: 23341
ms.assetid: a41cd8de-9ee0-4275-aea5-131db5326e5b
ms.search.region: Global
ms.author: brking
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7d83d6536d85100ef6a91e909be5a8e57e423371
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/08/2020
ms.locfileid: "4693937"
---
# <a name="plan-for-the-global-address-book-and-other-address-books"></a>Planowanie globalnej książki adresowej i innych książek adresowych

[!include [banner](../includes/banner.md)]

W tym temacie opisano zagadnienia i decyzje, które należy uwzględnić w procesie planowania przed utworzeniem i skonfigurowaniem globalnej książki adresowej i wszelkich dodatkowych książek adresowych. Niektóre z decyzji obejmują potwierdzenie decyzji dokonanych w innych obszarów produktu, na przykład w hierarchii organizacyjnej.

## <a name="global-address-book"></a>Globalna książka adresowa

Przed rozpoczęciem pracy z globalną książką adresową, należy określić wartości domyślne dla niej. Wartości te są następnie używane do wszelkich dodatkowych książek adresowych utworzone przez Ciebie.

**Decyzje**

- W jakiej kolejności powinny być wyświetlane nazwy rekordów stron typu **Osoba**? Na przykład: nazwisko, drugie imię, imię.
- Czy rekordy stron mają być usuwane z książki adresowej po usunięciu rekordu roli? Wartości te są następnie używane do wszelkich dodatkowych książek adresowych utworzonych przez Ciebie.
- Czy podczas tworzenia nowego rekordu użytkownicy mają być zawiadamiani, jeśli zduplikowany rekord nie zostanie znaleziony w globalnej książce adresowej?
- Czy numer DUNS ma być uwzględniany w informacji rekordu strony?
- Czy jeśli numer DUNS jest uwzględniany w rekordzie strony, należy sprawdzić unikatowość numeru?
- Czy po utworzeniu rekordu strony w globalnej książce adresowej chcesz używać domyślnego typu strony, osoby lub organizacji?
- Które role użytkownik powinny mieć dostęp do prywatnych adresów i danych kontaktowych rekordów stron?

## <a name="additional-address-books"></a>Dodatkowe książki adresowe

Po utworzeniu w globalnej książki adresowej można utworzyć dodatkowe książki adresowe, np. oddzielne książki adresowe dla każdej firmy w organizacji lub dla każdego wiersza biznesowego. Na przykład firma Fabrikam jest międzynarodową organizacją mającą wiele firm i wiele obszarów działalności. Fabrikam planuje utworzyć książkę adresową dla każdego rodzaju działalności. Dla obszarów działalności, jakie pojawiają się w więcej niż jednej lokalizacji, takich jak narzędzia pneumatyczne, Fabrikam planuje utworzyć książkę adresową dla każdej lokalizacji. Chris, kierownik IT w firmie Fabrikam, utworzyć poniższą listę książek adresowych, które są wymagane. Ta lista zawiera rekordy stron, które każda książka adresowa musi zawierać.

- **Umowy dotyczące sektora publicznego (PubSC)** — rekordy stron dla wszystkich stron, które uczestniczą w umowach sektora publicznego, które posiada firma Fabrikam.
- **Umowy dotyczące sektora publicznego (PubSC)** — rekordy stron dla wszystkich stron, które uczestniczą w umowach sektora publicznego, które posiada firma Fabrikam.
- **Narzędzia elektroniczne (ET)** — rekordy stron dla wszystkich stron, które uczestniczą w kupowaniu/sprzedawaniu narzędzi elektronicznych lub które jakkolwiek inaczej mają styczność z narzędziami elektronicznymi dostarczanymi lub kupowanymi przez Fabrikam w firmie Fabrikam-Japonia.
- **Narzędzia pneumatyczne (PTJPN)** — rekordy stron dla wszystkich stron, które uczestniczą w kupowaniu/sprzedawaniu narzędzi pneumatycznych lub które jakkolwiek inaczej mają styczność z narzędziami pneumatycznymi dostarczanymi lub kupowanymi przez Fabrikam w firmie Fabrikam-Japonia.
- **Narzędzia pneumatyczne(PTUSA)** — rekordy stron dla wszystkich stron, które uczestniczą w kupowaniu/sprzedawaniu narzędzi pneumatycznych lub które jakkolwiek inaczej mają styczność z narzędziami pneumatycznymi dostarczanymi lub kupowanymi przez Fabrikam w firmie Fabrikam-USA.

**Decyzja:**

- Ile dodatkowych książek adresowych zostało utworzonych?


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]