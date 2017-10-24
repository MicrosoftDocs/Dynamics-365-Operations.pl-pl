---
title: "Planowanie sposobu konfiguracji globalnej książki adresowej i dodatkowych książek adresowych"
description: "W tym artykule opisano zagadnienia i decyzje, które należy uwzględnić w procesie planowania przed utworzeniem i skonfigurowaniem globalnej książki adresowej i wszelkich dodatkowych książek adresowych w programie Microsoft Dynamics 365 for Finance and Operations. Niektóre z decyzji obejmują potwierdzenie decyzji dokonanych w innych obszarów produktu, na przykład w hierarchii organizacyjnej."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DirAddressBook, DirAddressBookTeam, DirParameters, DirPartyTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 23341
ms.assetid: a41cd8de-9ee0-4275-aea5-131db5326e5b
ms.search.region: Global
ms.author: shiva.pandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 12bd0a02899c04b0511e2a50bc4a724d5074d13e
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="plan-how-to-configure-the-global-address-book-and-additional-address-books"></a>Planowanie sposobu konfiguracji globalnej książki adresowej i dodatkowych książek adresowych

[!include[banner](../includes/banner.md)]


W tym artykule opisano zagadnienia i decyzje, które należy uwzględnić w procesie planowania przed utworzeniem i skonfigurowaniem globalnej książki adresowej i wszelkich dodatkowych książek adresowych w programie Microsoft Dynamics 365 for Finance and Operations. Niektóre z decyzji obejmują potwierdzenie decyzji dokonanych w innych obszarów produktu, na przykład w hierarchii organizacyjnej.

<a name="global-address-book"></a>Globalna książka adresowa
-------------------

Przed rozpoczęciem pracy z globalną książką adresową, należy określić wartości domyślne dla niej. Wartości te są następnie używane do wszelkich dodatkowych książek adresowych utworzone przez Ciebie. 

**Decyzje:**

-   W jakiej kolejności powinny być wyświetlane nazwy rekordów stron typu **Osoba**? Na przykład: nazwisko, drugie imię, imię.
-   Czy rekordy stron mają być usuwane z książki adresowej po usunięciu rekordu roli? Wartości te są następnie używane do wszelkich dodatkowych książek adresowych utworzonych przez Ciebie.
-   Czy podczas tworzenia nowego rekordu użytkownicy mają być zawiadamiani, jeśli zduplikowany rekord nie zostanie znaleziony w globalnej książce adresowej?
-   Czy numer DUNS ma być uwzględniany w informacji rekordu strony?
-   Czy jeśli numer DUNS jest uwzględniany w rekordzie strony, należy sprawdzić unikatowość numeru?
-   Czy po utworzeniu rekordu strony w globalnej książce adresowej chcesz używać domyślnego typu strony, osoby lub organizacji?
-   Które role użytkownik powinny mieć dostęp do prywatnych adresów i danych kontaktowych rekordów stron?

## <a name="additional-address-books"></a>Dodatkowe książki adresowe
Po utworzeniu w globalnej książki adresowej można utworzyć dodatkowe książki adresowe, np. oddzielne książki adresowe dla każdej firmy w organizacji lub dla każdego wiersza biznesowego. Na przykład firma Fabrikam jest międzynarodową organizacją mającą wiele firm i wiele obszarów działalności. Fabrikam planuje utworzyć książkę adresową dla każdego rodzaju działalności. Dla obszarów działalności, jakie pojawiają się w więcej niż jednej lokalizacji, takich jak narzędzia pneumatyczne, Fabrikam planuje utworzyć książkę adresową dla każdej lokalizacji. Chris, kierownik IT w firmie Fabrikam, utworzyć poniższą listę książek adresowych, które są wymagane. Ta lista zawiera również rekordy stron, które każda książka adresowa musi zawierać.

-   **Umowy dotyczące sektora publicznego (PubSC)** — rekordy stron dla wszystkich stron, które uczestniczą w umowach sektora publicznego, które posiada firma Fabrikam.
-   **Umowy dotyczące sektora publicznego (PubSC)** — rekordy stron dla wszystkich stron, które uczestniczą w umowach sektora publicznego, które posiada firma Fabrikam.
-   **Narzędzia elektroniczne (ET)** — rekordy stron dla wszystkich stron, które uczestniczą w kupowaniu/sprzedawaniu narzędzi elektronicznych lub które jakkolwiek inaczej mają styczność z narzędziami elektronicznymi dostarczanymi lub kupowanymi przez Fabrikam w firmie Fabrikam-Japonia.
-   **Narzędzia pneumatyczne (PTJPN)** — rekordy stron dla wszystkich stron, które uczestniczą w kupowaniu/sprzedawaniu narzędzi pneumatycznych lub które jakkolwiek inaczej mają styczność z narzędziami pneumatycznymi dostarczanymi lub kupowanymi przez Fabrikam w firmie Fabrikam-Japonia.
-   **Narzędzia pneumatyczne(PTUSA)** — rekordy stron dla wszystkich stron, które uczestniczą w kupowaniu/sprzedawaniu narzędzi pneumatycznych lub które jakkolwiek inaczej mają styczność z narzędziami pneumatycznymi dostarczanymi lub kupowanymi przez Fabrikam w firmie Fabrikam-USA.

**Decyzja:**

-   Ile dodatkowych książek adresowych zostało utworzonych?

### <a name="address-book-security"></a>Zabezpieczenia książki adresowej

W dowolnym momencie można utworzyć książki adresowe i w dowolnym momencie można również ustawić parametry zabezpieczeń książki adresowej. Ustawianie uprawnień zabezpieczeń dla książki adresowej nie jest konieczne, ale w przeciwnym wypadku wszyscy pracownicy w firmie mogą wyświetlić wszystkie rekordy jednostek w tej książce adresowej. Można ustawić uprawnienia zabezpieczeń do rekordów stron za pomocą książki adresowej. Uprawnienia zabezpieczeń są oparte na zespołach. Takie rozwiązanie gwarantuje, że tylko pracownicy, którzy są przypisani do zespołu, mają dostęp do książki adresowej i mogą wyświetlić rekordy stron w tej książce adresowej. Musisz wybrać zespoły, które mają dostęp do każdej z książek adresowych. Dla każdej książki adresowej można ustawić uprawnienia zabezpieczeń, które przyznają lub blokują dostęp do określonych zespołów. Po udostępnieniu zespołowi uprawnień dostępu do książki adresowej jego członkowie mogą wyświetlać jej rekordy. Jeśli nie przyznasz zespołowi dostępu do książki adresowej, członkowie zespołu nie mogą wyświetlać książki adresowej ani jej zawartości. 

**Decyzja:**

-   Które zespoły mają dostęp do każdej nowej książki adresowej, którą chcesz utworzyć?





