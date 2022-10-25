---
title: Synchronizacja inspekcji operacji klienta w programie headquarters
description: W tym artykule opisano, jak w ramach inspekcji synchronizować operacje klientów w programie Microsoft Dynamics 365 Commerce headquarters, aby rozwiązać ewentualne problemy użytkowników witryny.
author: gvrmohanreddy
ms.date: 10/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-09-28
ms.openlocfilehash: c615b0b436e01a1423b5611a72f0056b5b14f8e8
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691092"
---
# <a name="audit-synchronization-of-customer-operations-in-headquarters"></a>Synchronizacja inspekcji operacji klienta w programie headquarters

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

W tym artykule opisano, jak w ramach inspekcji synchronizować operacje klientów w programie Microsoft Dynamics 365 Commerce headquarters, aby rozwiązać ewentualne problemy użytkowników witryny.

Gdy organizacje zaczynają implementować możliwość asynchronicznego tworzenia i edytowania klientów, administratorzy witryny muszą mieć sposób na przeglądanie operacji i rozwiązywanie pokrewnych problemów na podstawie żądań użytkowników witryny lub błędów procesów. W tych scenariuszach administratorzy witryn powinni mieć możliwość inspekcji operacji tworzenia i edytowania klientów oraz naprawiania wszelkich błędów przy użyciu modelu samoobsługi.

## <a name="customer-synchronization-status"></a>Stan synchronizacji odbiorcy

Gdy wyrazisz zgodę na korzystanie z trybu asynchronicznego zarządzania klientami i odpowiednich funkcji, administratorzy programu Commerce headquarters muszą tworzyć i planować cykliczne zadanie wsadowe dla **zadania P**, zadania **Synchronizowanie klientów i partnerów biznesowych z trybu asynchronicznego** oraz zadanie **1010**, aby dowolni klienci asynchroniczni byli konwertowani na klientów synchronicznych w programu Commerce headquarters. Synchronizacja operacji zarządzania klientami następuje przy każdym uruchomieniu tych zadań. Aby uzyskać więcej informacji, zobacz [Tryb tworzenia klientów asynchronicznych](async-customer-mode.md).

Jako właściciel firmy możesz wykonywać następujące operacje:

- Wyświetlanie wszystkich operacji tworzenia/edytowania użytkowników witryny. Szczegóły obejmują stan i znacznik czasu.
- Filtrowanie operacji przy użyciu pól i wartości tabeli klientów w celu zawężenia zakresu dziennika inspekcji.
- Wyświetlanie krótkich opisów zmian oraz szczegółów stanu w celu zrozumienia operacji na wysokim poziomie.
- W przypadku błędów edytuj i popraw pola z problemami, a następnie zapisz i zsynchronizuj określone operacje klientów.

### <a name="elements-on-the-customer-synchronization-status-page"></a>Elementy na stronie Stan synchronizacji klienta

Aby wyświetlić listę wszystkich operacji synchronizacji, w programie Commerce headquarters przejdź do pozycji **Handel detaliczny i inny \> Klienci \> Stan synchronizacji klienta**. Na poniższej ilustracji pokazano przykład strony **Stan synchronizacji klienta**.

![Strona stanu synchronizacji klienta w programie Commerce headquarters.](media/D365-Commerce-Customer-Mgmt-Audi-Async-Operations.png)

Domyślnie lista operacji synchronizacji klienta po lewej na stronie **Stan synchronizacji klienta** zawiera następujące kolumny:

- Nazwa kanału
- Konto odbiorcy
- Asynchroniczne konto odbiorcy
- Znacznik czasu operacji
- Stan synchronizacji klienta

W prawym górnym rogu strony są przedstawiane szczegóły konta klienta, takie jak wartości pól **Konto klienta**, **Operacja asynchroniczna handlu detalicznego**, **Stan synchronizacji klienta** i **Ostatni znany błąd**.

Sekcja **Opis zmiany** zawiera opis typu uruchomionej operacji zarządzania klientami (na przykład szczegóły tworzenia klienta, aktualizacji konta lub niepowodzenia synchronizacji).

Sekcja **Atrybuty klienta** zawiera siatkę ze wszystkimi atrybutami klienta oraz ich starymi i nowymi wartościami. Tę sekcję można edytować, jeśli chcesz zmienić wartości atrybutów klienta, aby poprawić usterki, a następnie ponownie zsynchronizować dane.
