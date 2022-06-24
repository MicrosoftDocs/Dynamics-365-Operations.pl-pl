---
title: Zarządzanie klientami w sklepach
description: W tym artykule wyjaśniono, w jaki sposób detaliści mogą włączyć funkcje zarządzania klientami w punkcie sprzedaży (POS) w Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 12/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 805d0b5894b18e2fc34f481bdc32ada7a4b1aee0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8863494"
---
# <a name="customer-management-in-stores"></a>Zarządzanie klientami w sklepach

[!include [banner](includes/banner.md)]

W tym artykule wyjaśniono, w jaki sposób detaliści mogą włączyć funkcje zarządzania klientami w punkcie sprzedaży (POS) w Microsoft Dynamics 365 Commerce.

Bardzo ważne jest, aby skojarzyć ze sklepem możliwość tworzenia i edytowania rekordów odbiorcy w POS. W ten sposób mogą przechwytywać wszelkie aktualizacje informacji o odbiorcy, takie jak adres e-mail, numer telefonu i adres. Te informacje są pomocne w przypadku systemów przetwarzania od odbiorcy do odbiorcy, takich jak marketing, ponieważ ich efektywność zależy od dokładności danych klientów.

Skojarzenia sprzedaży mogą wyzwalać przepływ pracy tworzenia odbiorcy z dwóch punktów wejścia punktu sprzedaży. Mogą wybrać przycisk zamapowany na operację **Dodawania odbiorcy** lub wybrać pozycję **Utwórz klienta** na pasku aplikacji na stronie wyników wyszukiwania. W obu wypadkach zostanie wyświetlone okno dialogowe **Nowy odbiorca**, w którym skojarzeń ze sprzedażą może wprowadzić wymagane dane odbiorcy, takie jak imię i nazwisko, adres e-mail, numer telefonu, adres oraz wszelkie dodatkowe informacje związane z firmą. Te dodatkowe informacje można przechwytywać przy użyciu atrybutów odbiorcy, które są skojarzone z tym klientem. Aby uzyskać więcej informacji o atrybutach odbiorcy, zobacz temat [Atrybuty odbiorcy](dev-itpro/customer-attributes.md).

Skojarzenia sprzedaży mogą także przechwytywać pomocnicze adresy e-mail i numery telefonów. Ponadto mogą przechwytywać preferencje odbiorcy dotyczące otrzymywania informacji marketingowych za pośrednictwem dowolnego z tych pomocniczych adresów e-mail lub numerów telefonów. Aby włączyć tę funkcję, sprzedawcy detaliczni muszą włączyć funkcję **Przechwytywanie wielu wiadomości e-mail i numerów telefonów oraz zgody na marketing dla tych kontaktów** w obszarze roboczym **Zarządzanie funkcjami** w programie Commerce Headquarters (**Administrowanie systemem \> Obszary robocze \> Zarządzanie funkcjami**).

## <a name="default-customer-properties"></a>Domyślne właściwości odbiorcy

Sprzedawcy detaliczni mogą używać strony **Wszystkie sklepy** w programie Commerce Headquarters (**Retail i Commerce \> Kanały \> Sklepy**), aby skojarzyć domyślnego klienta z każdym sklepem. Następnie program Commerce kopiuje właściwości zdefiniowane dla odbiorcy domyślnego do wszystkich utworzonych rekordów nowych klientów. Na przykład w oknie dialogowym **Tworzenie odbiorcy** są wyświetlane właściwości dziedziczone po domyślnym odbiorcy skojarzonym ze sklepem. Te właściwości obejmują **typ odbiorcy**, **grupę klientów**, **opcje dotyczące paragonu**, **e-mail dla paragonu**, **walutę** i **język**. Wszystkie **przynależności** (grupy odbiorców) są także dziedziczone po odbiorcy domyślnym. **Wymiary finansowe** są jednak dziedziczone po grupie klientów skojarzonej z domyślnym klientem, a nie po samym odbiorcy domyślnym.

> [!NOTE]
> Wartość **e-mail odbiorcy** zostanie skopiowana z klienta domyślnego tylko w przypadku, gdy dla nowo utworzonych klientów nie zostanie podany identyfikator e-mail paragonu. Oznacza to, że jeśli identyfikator e-mail paragonu jest obecny przy domyślnym kliencie, to wszyscy klienci utworzeni z witryny e-commerce otrzymają ten sam identyfikator e-mail, ponieważ nie ma interfejsu użytkownika do przechwytywania identyfikatora e-mail paragonu od klienta. Zalecamy pozostawienie pola **e-mail dla paragonu** pustego dla domyślnego klienta sklepu i korzystanie z niego tylko w przypadku, gdy proces biznesowy jest uzależniony od obecności adresu e-mail paragonu. 

Skojarzenia sprzedaży mogą przechwytywać wiele adresów dla odbiorcy. Imię i nazwisko odbiorcy oraz numer telefonu są dziedziczone z informacji kontaktowych skojarzonych z każdym adresem. Skrócona karta **Adresy** rekordu odbiorcy zawiera pole **Cel**, które mogą edytować skojarzenia sprzedaży. Jeśli typem odbiorcy jest **Osoba**, domyślną wartością jest **Strona główna**. Jeśli typem odbiorcy jest **Organizacja**, domyślną wartością jest **Biznes**. Inne wartości, które obsługuje to pole, obejmują: **Strona główna**, **Biuro** i **Poczta**. Wartość pola **Kraj** w adresie jest dziedziczona z adresu podstawowego określonego na stronie **Jednostka operacyjna** w Commerce headquarters w **Administrowanie organizacją \> Organizacje \> Jednostki organizacyjne**.



## <a name="additional-resources"></a>Dodatkowe zasoby

[Asynchroniczny tryb tworzenia klientów](async-customer-mode.md)

[Konwertowanie klientów asynchronicznych na synchronicznych](convert-async-to-sync.md)

[Atrybuty odbiorcy](dev-itpro/customer-attributes.md)

[Wykluczanie danych w trybie offline](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)
