---
title: Asynchroniczny tryb tworzenia klientów
description: W tym artykule opisano asynchroniczny tryb tworzenia klientów w aplikacji Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 10/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-12-17
ms.openlocfilehash: b2926339021991f87dd3eadef94da3b500c954cf
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690297"
---
# <a name="asynchronous-customer-creation-mode"></a>Asynchroniczny tryb tworzenia klientów

[!include [banner](includes/banner.md)]

W tym artykule opisano asynchroniczny tryb tworzenia klientów w aplikacji Microsoft Dynamics 365 Commerce.

W aplikacji Commerce istnieją dwa tryby tworzenia klientów: synchroniczny i asynchroniczny. Domyślnie odbiorcy są tworzona synchronicznie. Są one tworzone w programie Commerce Headquarters w czasie rzeczywistym. Synchroniczny tryb tworzenia klientów jest korzystny, ponieważ nowi odbiorcy mogą od razu podlegać wyszukiwaniu w różnych kanałach. Ma jednak także minusy. Ponieważ generuje on wywołania usługi [Commerce Data Exchange: Real-time Service](dev-itpro/define-retail-channel-communications-cdx.md#realtime-service) może to mieć wpływ na wydajność, jeśli wywołanych jest wiele równoczesnych wywołań tworzenia klientów.

Jeśli dla opcji **Utwórz odbiorcy w trybie asynchronicznym** jest ustawiona wartość **Tak** w profilu funkcji sklepu (**Retail i Commerce \> Ustawienia kanału \> Ustawienia sklepu online \> Profile funkcji**), wywołania usługi Real-time Service nie są używane do tworzenia rekordów klientów w bazie danych kanału Asynchroniczny tryb tworzenia klientów nie ma wpływu na wydajność centrali w programie Commerce Headquarters. Tymczasowy unikatowy identyfikator GUID jest przypisywany do każdego nowego asynchronicznego rekordu klienta i używany jako identyfikator konta klienta. Ten identyfikator GUID nie jest widoczny dla użytkowników w punkcie sprzedaży. Zamiast tego ci użytkownicy zobaczą identyfikator konta odbiorcy **Oczekująca synchronizacja**.

> [!IMPORTANT]
> Zawsze gdy POS działa w trybie offline, system automatycznie tworzy klientów asynchronicznie, nawet gdy tryb asynchronicznego tworzenia klientów jest wyłączony. Dlatego niezależnie od wyboru między synchronizacją a asynchronicznym tworzeniem klientów, administratorzy Commerce headquarters muszą tworzyć i planować cykliczne zadanie wsadowe dla **zadania P**, zadania **Synchronizowanie klientów i partnerów biznesowych z trybu asynchronicznego** oraz zadanie **1010**, aby dowolni odbiorcy asynchroniczni byli konwertowani na odbiorców synchronicznych w centrali Commerce.

## <a name="async-customer-limitations"></a>Ograniczenia dotyczące odbiorcy usługi Async

Funkcje klientów asynchronicznych mają obecnie następujące ograniczenia:

- Nie można wystawiać kart lojalnościowych dla odbiorców asynchronicznych, chyba że nowy identyfikator konta odbiorcy zostanie zsynchronizowany z powrotem z kanałem.

## <a name="async-customer-enhancements"></a>Ulepszenia dotyczące klientów asynchronicznych

Aby pomóc organizacjom korzystać z trybu tworzenia klientów asynchronicznych do zarządzania klientami i ograniczyć komunikację w czasie rzeczywistym z Commerce headquarters, wprowadzono następujące ulepszenia, aby zapewnić parzystość między trybami synchronizacji i asynchronicznym w kanałach. 

| Udoskonalenie funkcji | Wersja Commerce | Szczegóły funkcji |
|---|---|---|
| Poprawa wydajności, gdy informacje o kliencie są pobierane z bazy danych kanału | 10.0.20 i nowsze wersje | Aby zwiększyć wydajność, jednostka odbiorcy jest dzielona na mniejsze jednostki. Następnie z bazy danych kanału są pobierane tylko wymagane informacje. |
| Możliwość asynchronicznego tworzenia adresu podczas realizacji zamówienia | 10.0.22 i nowsze wersje | <p>Przełącznik funkcji: **Włączanie tworzenia asynchronicznego dla adresów odbiorcy**</p><p>Szczegóły funkcji:</p><ul><li>Możliwość dodawania adresów bez tworzenia wywołań usługi Real-time Service w Commerce headquarters</li><li>Możliwość jednoznacznej identyfikacji adresów w bazie danych kanału bez użycia identyfikatora rekordu (wartość **RecId**)</li><li>Sygnatura czasowa śledzenia przy tworzeniu adresu</li><li>Synchronizacja adresów w programie Commerce Headquarters</li></ul><p>Ta funkcja wpływa zarówno na odbiorców synchronizacji, jak i odbiorców asynchronicznych. Aby oprócz asynchronicznego tworzenia adresów edytować adresy asynchronicznie, należy włączyć funkcję **Edytowanie odbiorców w trybie asynchronicznym**.</p> |
| Włącz parzystość między tworzeniem synchronicznym i asynchronicznym odbiorcy. | 10.0.24 i nowsze wersje | <p>Włączanie funkcji: **Włącz rozszerzone tworzenie odbiorcy asynchronicznego.**</p><p>Szczegóły funkcji: możliwość przechwytywania dodatkowych informacji, takich jak tytuł, przynależności od klienta domyślnego i dodatkowe informacje kontaktowe (numer telefonu i adres e-mail), podczas gdy tworzysz klientów asynchronicznie</p> |
| Komunikaty o błędach wyświetlane w interfejsie użytkownika | 10.0.28 i nowsze wersje | Te ulepszenia pomagają ulepszyć przyjazne dla użytkownika komunikaty o błędach, jeśli użytkownik nie może natychmiast edytować informacji podczas trwania synchronizacji. Ulepszenia te można włączyć za pomocą funkcji **Zezwalaj na niemodyfikowalne niektóre elementy interfejsu użytkownika** przez **Ustawienia witryny \> Rozszerzenia** w Konstruktorze witryn Commerce. |
| Możliwość asynchronicznej edycji informacji o odbiorcy | 10.0.29 i nowsze wersje | <p>Włączanie funkcji: **Włącz edytowanie odbiorców w trybie asynchronicznym**</p><p>Szczegóły funkcji: możliwość asynchronicznej edycji danych odbiorcy</p><p>Aby uzyskać odpowiedzi na typowe pytania dotyczące problemów związanych z asynchronicznym edytowaniem informacji o odbiorcy, zobacz [Często zadawane pytania dotyczące trybu asynchronicznego tworzenia odbiorcy](async-customer-mode-faq.md).</p> |
| Możliwość prowadzenia inspekcji synchronizacji operacji zarządzania klientami | 10.0.31 i nowsze wersje | To udoskonalenie umożliwia użytkownikom inspekcję synchronizacji operacji zarządzania klientami w programie Commerce Headquarters. Ponadto umożliwia ono użytkownikom wprowadzanie zmian i synchronizowanie danych w razie potrzeby. |

### <a name="feature-switch-hierarchy"></a>Hierarchia przełącznika funkcji

Ze względu na hierarchię przełączników funkcji przed włączeniem funkcji **Włącz edytowanie odbiorców w trybie asynchronicznym**, należy włączyć następujące funkcje: 

- **Usprawnienia wydajności zamówień klientów i transakcji klientów** — ta funkcja jest obowiązkowa od czasu wydania 10.0.28 systemu Commerce. 
- **Włącz rozszerzone tworzenie odbiorcy asynchronicznego**
- **Włączanie tworzenia asynchronicznego dla adresów odbiorcy**

Aby uzyskać odpowiedzi na typowe pytania rozwiązywania problemów, zobacz [Często zadawane pytania dotyczące trybu asynchronicznego tworzenia klientów](async-customer-mode-faq.md). 

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
