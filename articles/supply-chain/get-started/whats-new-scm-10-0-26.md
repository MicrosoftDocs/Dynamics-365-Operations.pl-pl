---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 Supply Chain Management 10.0.26 (Maj 2022 r.)
description: W tym artykule opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 Supply Chain Management 10.0.26.
author: kamaybac
ms.date: 03/01/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-03-01
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: 8be79f259505c084a8680c453ec15a4cef1a890f
ms.sourcegitcommit: 873d66c03a51ecb7082e269f30f5f980ccd9307f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2022
ms.locfileid: "9124507"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10026-may-2022"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 Supply Chain Management 10.0.26 (Maj 2022 r.)

[!include [banner](../includes/banner.md)]

W tym artykule wymieniono nowe oraz zmienione funkcje dostępne w programie Microsoft Dynamics 365 Supply Chain Management w wersji 10.0.26. Ta wersja ma numer kompilacji 10.0.1192 i jest dostępna w następujący sposób:

- **Wersja podglądu:** marzec 2022
- **Ogólna dostępność wydania (Samoaktualizacja):** kwiecień 2022 r.
- **Ogólna dostępność wydania (automatyczna aktualizacja):** maj 2022 r.

## <a name="features-included-in-this-release"></a>Funkcje zawarte w tym wydaniu

To wydanie zawiera funkcje, które są podane w następującej tabeli. Firma Microsoft może zaktualizować ten artykuł w taki sposób, aby zawierał funkcje wprowadzone do kompilacji po początkowym opublikowaniu tego artykułu.

| Obszar funkcji | Funkcja | Więcej informacji | Włączone przez   |
|---|---|---|---|
| Zapasy i logistyka | [Wyszukiwanie dostępnych zapasów w celu obsługi zaawansowanych pozycji zarządzania magazynem](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/inventory-visibility-support-advanced-warehouse-management) | [Obsługa dodatku Inventory Visibility dla pozycji WMS](../inventory/inventory-visibility-whs-support.md) | Zarządzanie funkcjami:<br>*Włącz pozycje magazynowe w Widoczności magazynu* |
| Zapasy i logistyka | [Dostępne zapasy dla dodatku Widoczność zapasów](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/available-to-promise-inventory-visibility-add-in) | [Widoczność dostępnych zapasów — harmonogramy zmian i dostępność zapasów](../inventory/inventory-visibility-available-to-promise.md) | Włączone przez konfigurację usługi |
| Produkcja | [Pozycje wagi wychwytu dla interfejsu wykonawczego hali produkcyjnej](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/catch-weight-items-production-floor-execution-interface) | [Jak pracownicy korzystają z interfejsu wykonania hal produkcyjnych](../production-control/production-floor-execution-use.md) | Zarządzanie funkcjami:<br>*(Wersja zapoznawcza) Raport pozycji ilości efektywnej z interfejsu wykonania hal produkcyjnych* |
| Produkcja | Moja karta zadań w interfejsie wykonania hal produkcyjnych <!-- KFM: Add link to release plan when available --> | [Jak pracownicy korzystają z interfejsu wykonania hal produkcyjnych](../production-control/production-floor-execution-use.md) | Zarządzanie funkcjami:<br>*Moja karta zadań w interfejsie wykonania hal produkcyjnych* |

## <a name="feature-enhancements-included-in-this-release"></a>Ulepszenia funkcji zawarte w tym wydaniu

W poniższej tabeli wymieniono rozszerzenia funkcji, które są zawarte w tym wydaniu. Każde z tych rozszerzeń zapewnia stopniowe ulepszanie istniejącej funkcji. Ponieważ są to tylko rozszerzenia, nie są one wymienione w [planie wydawniczym](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Aby jednak mieć pewność, że te ulepszenia nie będą kolidować z istniejącymi ustawieniami lub preferencjami użytkownika, każde z nich jest domyślnie wyłączone (chyba że zaznaczono inaczej).

Aby włączyć lub wyłączyć te funkcje, należy przejść do obszaru [zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Moduł | Nazwa funkcji w zarządzaniu funkcjami | Więcej informacji |
|---|---|---|
| Zaopatrzenie i sourcing | Księguj zarejestrowane ilości produktów magazynowanych i reszty produktów niemagazynowanych dla dokumentów dostawy i faktur od dostawcy | Ta funkcja zmienia sposób, w jaki ilości produktów nie magazynowanych (takich jak usługi) są księgowane podczas przetwarzania faktur dostawcy i wysyłek przychodzących zgodnie z zamówieniami zakupu. Ta funkcja modyfikuje zachowanie opcji *Zarejestrowane ilości i ilości usług do księgowania przychodów i faktur dostawców*, zmieniając ją tak, aby była zgodne z zachowaniem opcji *Zarejestrowana ilość i produkty nie magazynowane* już dostarczone podczas księgowania ilości dla dokumentów dostawy sprzedaży.<br><br>W przypadku zaksięgowania dokumentu przyjęcia produktów lub faktury od dostawcy za pomocą opcji *Zarejestrowane ilości i ilości usług* system księguje zarejestrowaną ilość produktów magazynowanych i księguje pozostałą ilość produktów niematurowanych (w tym zarówno usług, jak i usług). Bez tej funkcji system nadal księguje zarejestrowaną ilość produktów magazynowanych (w tym usługi skonfigurowane jako towary magazynowe), ale zawsze księguje pełną zamówione ilości produktów usług nie magazynowanych (i ignoruje produkty nie magazynowane, które nie są typu *Usługa*). |
| Zaopatrzenie i sourcing | Synchronizuj wymiary śledzenia w międzyfirmowych wierszach sprzedaży i zamówienia zakupu | Ta funkcja umożliwia kontrolowanie, czy wymiary śledzenia numerów seryjnych i numerów partii są synchronizowane w wierszach międzyfirmowego zamówienia sprzedaży i zakupu. Dodaje nowe ustawienia do kart **Zasady zamówień zakupu** i **Zasady zamówień sprzedaży** na stronie konfiguracji **Międzyfirmowe** dla klientów i dostawców. Ponadto uaktualnia nazwy kilku powiązanych z nim ustawień w pobliżu.<br><br>Jeśli korzystasz z procesów zarządzania magazynem (WMS), pamiętaj, że ta funkcja synchronizuje numery partii i seryjne tylko wtedy, gdy te wymiary znajdują się powyżej lokalizacji w hierarchii rezerwacji miejsca docelowego. |
| Zarządzanie informacjami o produktach | Wyczyść wartości atrybutów produktów | Ta funkcja dodaje okresowe zadanie o nazwie **Wyczyść wartości atrybutów produktów** czyszczące rekordy wartości atrybutów produktów, które nie są już skojarzone z żadnym produktem za pośrednictwem kategorii produktów. |
| Zarządzanie zapasami i magazynem | (Rosja) Zapobieganie rozbieżnościom podczas wystawiania deklaracji GTD dla zamówień zakupu, które zawierają pozycje z obsługą funkcji WMS | Ta funkcja jest dostępna tylko w języku rosyjskim. Zapobiega to rozbieżnościom, które występują podczas wystawiania rosyjskich numerów deklaracji celnych (GTD) dla zamówień zakupu importu, które zawierają towary włączone dla procesów zarządzania magazynem (WMS). Proces wydawania GTD zmienia niektóre wartości wymiarów magazynowych w powiązanych transakcjach magazynowych na fakturach zawartych w arkuszu niestandardowym, co prowadzi do rozbieżności między rekordami pracy dla zamówienia zakupu a transakcjami magazynowymi dla zakupu. Gdy ta funkcja jest włączona, proces wydawania GTD generuje pracę korekty, która eliminuje takie rozbieżności. |
| Zarządzanie magazynem | Ulepszone analizowanie kodów kreskowych GS1 | Ta funkcja dodaje rozszerzoną analizę danych symbolu GS1. Nowy program parserowy implementuje algorytm specyfikacji ogólnej GS1 na celu analizowanie symboli GS1 i zapewnia silniejszą weryfikację danych. Aby uzyskać więcej informacji, zobacz [Skanowanie kodów kreskowych GS1](../warehousing/gs1-barcodes.md). |
| Zarządzanie magazynem | Nowe strony pulpitu planowania wysyłki ładunku | Dodaje dwie nowe strony pulpitu planowania wysyłki ładunku: **Pulpit planowania wysyłki ładunku przychodzącego** i **Pulpit planowania wysyłki ładunku wychodzącego**. |
| Zarządzanie magazynem | Aplikacja zarządzania magazynem — pusta deklaracja GTD | Ta funkcja jest dostępna tylko w języku rosyjskim. Dzięki tej aplikacji pracownicy korzystający z aplikacji mobilnej Warehouse Management w razie potrzeby pozostawią puste numery rosyjskich deklaracji celnych (GTD). Jeśli wymiar śledzenia GTD jest tak ustawiony, że zezwala na puste wartości, system akceptuje puste wartości GTD dla operacji magazynowych pod warunkiem, że są dostępne zapasy. |

## <a name="new-and-updated-documentation-resources"></a>Nowe i zaktualizowane zasoby dokumentacji

Niedawno dodano lub znacząco zaktualizowano następujące artykuły pomocy. Te artykuły nie zawsze są związane z nowymi funkcjami dodanymi w tym wydaniu, jak wymieniono w poprzedniej sekcji. Mogą jednak ułatwić efektywniejsze korzystanie z istniejących funkcji..

| Obszar funkcji | Nowe lub zaktualizowane artykuły |
|---|---|
| Zarządzanie kosztami | Zaktualizowane przykłady i diagramy zostały dodane do każdego z następujących artykułów:<ul><li>[FIFO z wartością fizyczną i oznaczeniami](../cost-management/fifo-physical-value-marking.md)</li><li>[LIFO z wartością fizyczną i oznaczeniami](../cost-management/lifo-physical-value-marking.md)</li><li>[LIFO wg daty z wartością fizyczną i oznaczeniami](../cost-management/lifo-date-physical-value-marking.md)</li><li>[Średnia krocząca kosztu własnego](../cost-management/running-average-cost-price.md)</li><li>[Średnia ważona z wartością fizyczną i oznaczeniami](../cost-management/weighted-average-physical-value-marking.md)</li></ul> |

## <a name="additional-resources"></a>Dodatkowe zasoby

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aktualizacja Platform dla aplikacji finansowych i operacyjnych

Pakiet Microsoft Dynamics 365 Supply Chain Management 10.0.26 zawiera aktualizację platformy. Aby dowiedzieć się więcej, zobacz [aktualizacje platformy dla wersji 10.0.26 aplikacji finansowych i operacyjnych (maj 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-26.md).

### <a name="bug-fixes"></a>Poprawki błędów

Aby uzyskać informacje dotyczące poprawek usterek zawartych w każdej aktualizacji, która jest częścią 10.0.26, należy zalogować się do Lifecycle Services (LCS) i wyświetlić [artykuł z bazy wiedzy](https://fix.lcs.dynamics.com/Issue/Details?bugId=662864).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-1-plan"></a>Dynamics 365 i chmury branżowe: plan aktualizacji 1 wersji z 2022 r.

Interesują Cię nadchodzące i ostatnio wprowadzone możliwości którejkolwiek z naszych aplikacji lub platform biznesowych?

Zapoznaj się z tematem [Dynamics 365 i chmury branżowe: plan aktualizacji 1 wersji z 2022 r.](/dynamics365-release-plan/2022wave1/). Zebraliśmy w jednym dokumencie wszystkie szczegóły, których możesz używać na potrzeby planowania.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Usunięte i przestarzałe funkcje Supply Chain Management

W artykule [Usunięte lub przestarzałe funkcje w Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) opisano funkcje, które są wycofane lub zostały zaplanowane do usunięcia w Supply Chain Management.

- *Usunięta* funkcja nie jest już dostępna w produkcie.
- *Przestarzała* funkcja nie jest aktywnie tworzona i może zostać usunięta w przyszłej aktualizacji.

Zanim jakakolwiek funkcja zostanie usunięta z produktu, powiadomienie o zaniechaniu będzie anonsowane w sekcji artykułu na temat [usuniętych lub przestarzałych funkcji w Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 miesięcy przed usunięciem.

W przypadku zmian, które wpływają tylko na czas kompilacji, ale są zgodne z trybem piaskownicy i środowiskami produkcyjnymi, czas niezgodności będzie krótszy niż 12 miesięcy. Zazwyczaj są to aktualizacje funkcjonalne, które należy wykonać w kompilatorze.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

