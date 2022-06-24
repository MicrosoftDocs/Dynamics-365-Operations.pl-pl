---
title: Rozpoczęcie optymalizacji planowania
description: W tym artykule wyjaśniono, jak zacząć używanie funkcji optymalizacji planowania.
author: t-benebo
ms.date: 05/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: b9595aece264f55c706ebc84010b927fae56b512
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900978"
---
# <a name="get-started-with-planning-optimization"></a>Rozpoczęcie optymalizacji planowania

[!include [banner](../../includes/banner.md)]

Zgodnie ze [wcześniejszą informacją](../../get-started/removed-deprecated-features-scm-updates.md#use-of-built-in-supply-chain-management-master-planning-engine-for-distribution-scenarios), optymalizacja planowania zastąpi istniejący wbudowany aparat planowania głównego.

Jeśli obecnie jest używany wbudowany aparat planowania głównego, należy teraz rozpocząć planowanie migracji do optymalizacji planowania. Ważne jest natychmiastowe rozpoczęcie procesu migracji, ponieważ wymuszenie wycofania może mieć wpływ na operacje. Aby uniknąć wymuszania wycofania w ostatniej chwili, zdecydowanie zachęcamy do ukończenia migracji przed 1 grudnia 2020. 

Funkcja optymalizacji planowania nie obsługuje obecnie wszystkich funkcji dostępnych w aparacie planowania wbudowanym w rozwiązanie Supply Chain Management. Dlatego ważne jest, aby ocenić, czy aktualnie dostępna w optymalizacji planowania funkcja ma spełniać wymagania użytkownika. Funkcja optymalizacji planowania nie jest obecnie włączona domyślnie w usługach Dynamics Lifecycle Services (LCS), więc użytkownik ma możliwość wykonania oceny przed jej włączeniem.

> [!NOTE]
> Należy zażądać wyjątku od migracji do optymalizacji planowania, jeśli proces planowania głównego nie obejmuje produkcji (wygenerowane planowane zlecenia produkcyjne utworzone w ramach planowania głównego), a wbudowany aparat planowania głównego jest wymagany od wersji 10.0.15. Począwszy od wersji 10.0.16, w środowiskach, w których uruchomiono wbudowane planowanie główne bez generowania planowanych zleceń produkcyjnych, jest wyświetlany błąd. Optymalizacja planowania powinna być używana we wszystkich nowych wdrożeniach, które nie generują planowanych zleceń produkcyjnych podczas planowania głównego. Właściciele istniejących środowisk, w których uruchomiono wbudowany aparat planowania głównego bez generowania planowanych zleceń produkcyjnych, otrzymają wiadomości ze szczegółami dotyczącymi procesu wyjątku. Zalecamy współpracę z partnerem w celu oceny i planowania migracji do optymalizacji planowania.

Przed włączeniem optymalizacji planowania zdecydowanie zaleca się dokonanie oceny wyników analizy pasującej do optymalizacji planowania. Aby uzyskać więcej informacji, zobacz [Analiza dopasowywania optymalizacją planowania](planning-optimization-fit-analysis.md).

## <a name="availability"></a>Dostępność

Optymalizacja planowania jest obecnie dostępna w następujących regionach geograficznych platformy Azure: Stany Zjednoczone, Kanada, Europa, Zjednoczone Królestwo, Australia, Azja i Pacyfik, Brazylia, Japonia i Indie. W przypadku próby zainstalowania dodatku z innego regionu geograficznego usługi LCS wyświetlą komunikat informujący, że ten region geograficzny nie jest obsługiwany. Aby uzyskać więcej informacji o lokalizacjach geograficznych systemu Azure i pokrewnych regionach, zobacz [lokalizacje geograficznej systemu Azure](https://azure.microsoft.com/global-infrastructure/geographies/#geographies).

Pamiętaj, że optymalizacja planowania nie obsługuje wdrożeń lokalnych aplikacji Dynamics 365 Supply Chain Management.

## <a name="licensing"></a>Licencjonowanie

Jeśli planowanie główne można uruchomić za pomocą bieżącej licencji, nie trzeba kupować dodatkowej licencji, aby zacząć korzystać z optymalizacji planowania.

## <a name="install-and-enable-planning-optimization"></a>Instalowanie i włączanie optymalizacji planowania

Aby korzystać z optymalizacji planowania, musisz się upewnić, że w systemie są spełnione wszystkie wymagania wstępne, a następnie włącz klucz licencji i zainstaluj dodatek Optymalizacja planowania dla aplikacji Dynamics 365 Supply Chain Management.

### <a name="prerequisites"></a>Wymagania wstępne

Przed zainstalowaniem dodatku Optymalizacja planowania muszą zostać spełnione następujące wymagania wstępne:

- Musisz uruchamiać aplikację Supply Chain Management w środowisku wysokiej dostępności z włączonymi usługami LCS w warstwie 2 lub wyższej (nie środowisko OneBox) z aplikacją Dynamics 365 Supply Chain Management w wersji 10.0.7 lub nowszej. W przypadku próby zainstalowania dodatku w środowisku OneBox instalacja nie zostanie zakończona i trzeba będzie ją anulować.

- Należy skonfigurować system do integracji z platformą Power Platform. Aby uzyskać więcej informacji, zobacz [Integracja usługi Microsoft Power Platform z aplikacjami finansowymi i operacyjnymi](../../../fin-ops-core/dev-itpro/power-platform/overview.md).

### <a name="enable-the-planning-optimization-license"></a>Włączanie licencji optymalizacji planowania

Aby korzystać z optymalizacji planowania, należy włączyć klucz konfiguracji. W tym celu:

1. Ustaw system w trybie konserwacji, jak to opisano w sekcji [Tryb konserwacji](../../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Wybierz kolejno opcje **Administrowanie systemem \> Ustawienia \> Konfiguracja licencji**.
1. Na karcie **Klucze konfiguracji** zaznacz pole wyboru **Optymalizacja planowania**.
1. Wyłącz tryb konserwacji, jak to opisano w sekcji [Tryb konserwacji](../../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).

### <a name="install-the-planning-optimization-add-in"></a>Instalowanie dodatku Optymalizacja planowania

Musisz zainstalować dodatek z projektu usługi LCS i włączyć funkcję optymalizacji planowania z poziomu interfejsu użytkownika Supply Chain Management.

Aby zainstalować dodatek Optymalizacja planowania:

1. Zaloguj się do usługi LCS i otwórz żądane środowisko.
1. Przejdź do **Pełne szczegóły**.
1. Przewiń w dół do pozycji skróconej karty **Zarządzaj dodatkami środowiskowymi**.
1. Wybierz opcję **Zainstaluj nowy dodatek**.
1. Wybierz **Planowanie optymalizacji**.
1. Postępuj zgodnie z instrukcją instalacji i zaakceptuj warunki.
1. Wybierz **Zainstaluj**.
1. Na skróconej karcie **Dodatki środowiska** widać, czy jest instalowana Optymalizacja planowania.
1. Po kilku minutach **Instalowanie** zmieni się na **Zainstalowane** (konieczne może być odświeżenie strony). Po zainstalowaniu można już aktywować optymalizację planowania w systemie Dynamics 365 Supply Chain Management.

Głównym celem instalowania dodatku Optymalizacja planowania jest połączenie usługi i środowiska. Dlatego należy zainstalować dodatek oddzielnie dla każdego środowiska, w którym będzie używana Optymalizacja planowania, niezależnie od kodu przenoszonego między tymi środowiskami.

## <a name="integrate-planning-optimization-with-your-system"></a>Integrowanie optymalizacji planowania z systemem

Aby określić, czy dodatek optymalizacji planowania ma być używany w planowaniu głównym, należy przejść do **Planowanie główne** \> **Ustawienia** \> **Integracja optymalizacji planowania**.

### <a name="connection-status"></a>Stan połączenia

Stan połączenia wskazuje bieżący stan połączenia między Supply Chain Management a usługą optymalizacji planowania. Poniższa tabela przedstawia możliwe wartości.

| Stan połączenia | Opis | Czy można użyć optymalizacji planowania? |
|---|---|---|
| Połączono | Ustanowiono połączenie między usługą optymalizacji planowania i Supply Chain Management. | Tak |
| Włączanie połączenia | Obecnie trwa żądanie włączenia połączenia do usługi optymalizacji planowania. | Nie |
| Rozłączono | Nie istnieje połączenie z usługą optymalizacji planowania. Połączenie można włączyć z usługi LCS, jak opisano wcześniej w tym artykule. | Nie |
| Wyłączanie połączenia | Obecnie trwa żądanie wyłączania połączenia do usługi optymalizacji planowania. | Nie |
| Pobieranie informacji o stanie | System oczekuje na informacje o stanie z usługi optymalizacji planowania. | Nie |

### <a name="the-use-planning-optimization-option"></a>Opcja Zastosuj optymalizację planowania

Ustawienie opcji **Zastosuj optymalizację** planowania określa, który Aparat planowania będzie używany w planowaniu głównym:

- **Tak** — Optymalizacja planowania jest używana do planowania głównego.
- **Nie** – wbudowany silnik planowania Supply Chain Management jest używany do planowania głównego.

To ustawienie dotyczy wszystkich firm (osób prawnych). W niektórych firmach nie można używać optymalizacji planowania oraz wbudowanego planowania głównego w innych firmach.

> [!NOTE]
> Jeśli istniejące zadania wsadowe planowania utworzone dla wbudowanego silnika planowania Supply Chain Management dostaw są wyzwalane, a opcja **Użyj optymalizacji planowania** jest ustawiona na wartość **tak**, zadania te nie powiodą się.

### <a name="integration-with-the-setup"></a>Integracja z ustawieniami

Jeśli Optymalizacja planowania jest włączona, planowanie główne jest wykonywane przy użyciu dodatku Optymalizacja planowania. W takim przypadku wpływa to na wyniki i funkcje planowania głównego.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Warunki i postanowienia dla wersji zapoznawczej](https://go.microsoft.com/fwlink/?linkid=2015274)

[Omówienie optymalizacji planowania](planning-optimization-overview.md)

[Analiza dopasowywania optymalizacją planowania](planning-optimization-fit-analysis.md)

[Wyświetlanie dzienników historii i planowania planów](plan-history-logs.md)

[Stosowanie filtrów do planu](plan-filters.md)

[Anuluj planowanie pracy](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
