---
title: "Konfigurowanie książki adresowej."
description: "W tym artykule opisano zagadnienia i decyzje, które należy wykonać podczas procesu planowania, zanim instalacji i konfiguracji globalnej książce adresowej i wszelkie dodatkowe książki adresowe w usłudze Microsoft Dynamics 365 dla operacji. Niektóre z decyzji obejmują potwierdzenie decyzji dokonanych w innych obszarów produktu, na przykład w hierarchii organizacyjnej."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: DirAddressBook, DirAddressBookTeam, DirParameters, DirPartyTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 23341
ms.assetid: a41cd8de-9ee0-4275-aea5-131db5326e5b
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: abd9ec44530522657f758b35e8f987aa92c3b0e3
ms.lasthandoff: 03/31/2017


---

# <a name="configure-global-address-books"></a>Konfigurowanie książki adresowej.

W tym artykule opisano zagadnienia i decyzje, które należy wykonać podczas procesu planowania, zanim instalacji i konfiguracji globalnej książce adresowej i wszelkie dodatkowe książki adresowe w usłudze Microsoft Dynamics 365 dla operacji. Niektóre z decyzji obejmują potwierdzenie decyzji dokonanych w innych obszarów produktu, na przykład w hierarchii organizacyjnej.

<a name="global-address-book"></a>Globalna książka adresowa
-------------------

Przed rozpoczęciem pracy z globalną książką adresową, należy określić wartości domyślne dla niej. Wartości te są następnie używane do wszelkich dodatkowych książek adresowych utworzone przez Ciebie. **Decyzje:**

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

W dowolnym momencie można utworzyć książki adresowe i w dowolnym momencie można również ustawić parametry zabezpieczeń książki adresowej. Ustawianie uprawnień zabezpieczeń dla książki adresowej nie jest konieczne, ale w przeciwnym wypadku wszyscy pracownicy w firmie mogą wyświetlić wszystkie rekordy jednostek w tej książce adresowej. Można ustawić uprawnienia zabezpieczeń do rekordów stron za pomocą książki adresowej. Uprawnienia zabezpieczeń są oparte na zespołach. Takie rozwiązanie gwarantuje, że tylko pracownicy, którzy są przypisani do zespołu, mają dostęp do książki adresowej i mogą wyświetlić rekordy stron w tej książce adresowej. Musisz wybrać zespoły, które mają dostęp do każdej z książek adresowych. Dla każdej książki adresowej można ustawić uprawnienia zabezpieczeń, które przyznają lub blokują dostęp do określonych zespołów. Po udostępnieniu zespołowi uprawnień dostępu do książki adresowej jego członkowie mogą wyświetlać jej rekordy. Jeśli nie przyznasz zespołowi dostępu do książki adresowej, członkowie zespołu nie mogą wyświetlać książki adresowej ani jej zawartości. **Decyzja:**

-   Które zespoły mają dostęp do każdej nowej książki adresowej, którą chcesz utworzyć?



