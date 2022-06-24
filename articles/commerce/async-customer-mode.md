---
title: Asynchroniczny tryb tworzenia klientów
description: W tym artykule opisano asynchroniczny tryb tworzenia klientów w aplikacji Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 12/10/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-12-17
ms.openlocfilehash: 4ca63fe06a804035e976a3432454078c1cca0020
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880147"
---
# <a name="asynchronous-customer-creation-mode"></a>Asynchroniczny tryb tworzenia klientów

[!include [banner](includes/banner.md)]

W tym artykule opisano asynchroniczny tryb tworzenia klientów w aplikacji Microsoft Dynamics 365 Commerce.

W aplikacji Commerce istnieją dwa tryby tworzenia klientów: synchroniczny i asynchroniczny. Domyślnie odbiorcy są tworzona synchronicznie. Są one tworzone w programie Commerce Headquarters w czasie rzeczywistym. Synchroniczny tryb tworzenia klientów jest korzystny, ponieważ nowi odbiorcy mogą od razu podlegać wyszukiwaniu w różnych kanałach. Ma jednak także minusy. Ponieważ generuje on wywołania usługi [Commerce Data Exchange: Real-time Service](dev-itpro/define-retail-channel-communications-cdx.md#realtime-service) może to mieć wpływ na wydajność, jeśli wywołanych jest wiele równoczesnych wywołań tworzenia klientów.

Jeśli dla opcji **Utwórz odbiorcy w trybie asynchronicznym** jest ustawiona wartość **Tak** w profilu funkcji sklepu (**Retail i Commerce \> Ustawienia kanału \> Ustawienia sklepu online \> Profile funkcji**), wywołania usługi Real-time Service nie są używane do tworzenia rekordów klientów w bazie danych kanału Asynchroniczny tryb tworzenia klientów nie ma wpływu na wydajność centrali w programie Commerce Headquarters. Tymczasowy unikatowy identyfikator GUID jest przypisywany do każdego nowego asynchronicznego rekordu klienta i używany jako identyfikator konta klienta. Ten identyfikator GUID nie jest widoczny dla użytkowników w punkcie sprzedaży. Zamiast tego ci użytkownicy zobaczą identyfikator konta odbiorcy **Oczekująca synchronizacja**.

> [!IMPORTANT]
> Zawsze gdy POS działa w trybie offline, system automatycznie tworzy klientów asynchronicznie, nawet gdy tryb asynchronicznego tworzenia klientów jest wyłączony. Dlatego, niezależnie od wyboru między synchronicznym i asynchronicznym tworzeniem klienta, administratorzy centrali Commerce muszą utworzyć i zaplanować cykliczne zadanie wsadowe dla **zadania P**, czyli **Synchronizowanie odbiorców i partnerów biznesowych z zadania w trybie asynchronicznym** (nazywanego wcześniej zadaniem **synchronizacji klientów i partnerów biznesowych w trybie asynchronicznym**) oraz zadania **1010**, tak aby odbiorcy asynchroniczni byli konwertowani do odbiorców asynchronicznych w centrali Commerce.

## <a name="async-customer-limitations"></a>Ograniczenia dotyczące odbiorcy usługi Async

Funkcje klientów asynchronicznych mają obecnie następujące ograniczenia:

- Nie można edytować rekordów odbiorcy asynchronicznego, jeśli odbiorca nie zostanie utworzony w programie Commerce Headquarters i nowy identyfikator konta odbiorcy zostanie zsynchronizowany z powrotem z kanałem.
- Nie można wystawiać kart lojalnościowych dla odbiorców asynchronicznych, chyba że nowy identyfikator konta odbiorcy zostanie zsynchronizowany z powrotem z kanałem.

## <a name="async-customer-enhancements"></a>Ulepszenia dotyczące klientów asynchronicznych

W wersji Commerce 10.0.24 można włączyć funkcję **włączania rozszerzonego asynchronicznego tworzenia klientów** w obszarze roboczym **Zarządzanie funkcjami**. Ta funkcja eliminuje lukę między trybami tworzenia asynchronicznego i synchronicznego klientów w punkcie sprzedaży i handlu elektronicznym na następujące sposoby:

- Przynależności można skojarzyć z klientami asynchronicznym.
- Tytuły można dodawać do klientów asynchronicznych.
- Można przechwycić pomocnicze adresy e-mail i numery telefonów dla klientów asynchronicznych.

W wersji Commerce 10.0.22 można włączyć funkcję **włączania asynchronicznego tworzenia dla adresów klientów** w obszarze roboczym **Zarządzanie funkcjami**. Ta funkcja umożliwia asynchroniczne zapisywanie nowo utworzonych adresów klientów synchronicznych i asynchronicznych.

Po włączeniu wspomnianych wcześniej funkcji musisz zaplanować cykliczne zadanie wsadowe dla **zadania P**, zadania **Synchronizuj odbiorców i partnerów biznesowych z zadania w trybie asynchronicznym** oraz zadania **1010**, aby dowolni odbiorcy asynchroniczni byli konwertowani na odbiorców synchronizacji w centrali Commerce Headquarters.

### <a name="customer-creation-in-pos-offline-mode"></a>Tworzenie klienta w trybie offline POS

Jak wspomniano wcześniej, zawsze gdy punkt sprzedaży działa w trybie offline, system automatycznie tworzy klientów asynchronicznie, nawet gdy tryb asynchronicznego tworzenia klientów jest wyłączony. Dlatego administratorzy Commerce Headquarters muszą tworzyć i planować cykliczne zadanie wsadowe dla **zadania P**, zadania **Synchronizuj odbiorców i partnerów biznesowych w trybie asynchronicznym** oraz zadania **1010**, aby dowolni odbiorcy asynchroniczni są konwertowani na odbiorców synchronizacji w centrali Commerce Headquarters.

> [!NOTE]
> Jeśli dla opcji **Filtruj udostępnione tabele danych klientów** jest ustawiona wartość **Tak** na stronie **Schematu kanału sprzedaży** (**Retail i Commerce \> ustawienia Headquarters \> Harmonogram handlu \> Grupy baz danych kanału**), rekordy klientów nie są tworzone w trybie offline w punktach sprzedaży. Aby uzyskać więcej informacji, zobacz [Wykluczenie danych offline](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Zarządzanie klientami w sklepach](customer-mgmt-stores.md)

[Konwertowanie klientów asynchronicznych na synchronicznych](convert-async-to-sync.md)

[Atrybuty odbiorcy](dev-itpro/customer-attributes.md)

[Wykluczanie danych w trybie offline](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)
