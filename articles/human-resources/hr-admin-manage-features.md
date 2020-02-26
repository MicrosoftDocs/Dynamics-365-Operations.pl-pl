---
title: Zarządzanie funkcjami
description: Informacje o sposobie włączania i wyłączania nowych funkcji w systemie Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 84ff11e8237ce0669f7f6ac70c5b4411c5d4b466
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010173"
---
# <a name="manage-features"></a>Zarządzanie funkcjami

W ramach ciągłego wdrażania nowych funkcji zarządzania w aplikacji Microsoft Dynamics 365 Human Resources chcemy stworzyć klientom możliwość jak najszybszego zetknięcia się z nimi. Te funkcje są dostępne gdyż są prawie gotowe do ogólnego udostępnienia i przeszły wszechstronne testy. Jednak zanim je upublicznimy powszechnie, chcemy jeszcze poznać finalne opinie klientów i przeprowadzić ostatnią weryfikację.

Aby uzyskać więcej informacji o nowych funkcjach w aplikacji Human Resources, zobacz [Nowości i zmiany w aplikacji Human Resources](hr-admin-whats-new.md) oraz [Informacje o planie wydawniczym Dynamics 365 i Power Platform](https://docs.microsoft.com/dynamics365/release-plans/#pivot=products&panel=products1).

Obszar roboczy **zarządzanie funkcjami** zawiera listę funkcji dostarczanych w każdym wydaniu. Domyślnie nowe funkcje są wyłączone. Można użyć obszaru roboczego, aby włączyć je i wyświetlić dokumentację dla nich. Aby uzyskać więcej informacji o zarządzaniu funkcjami funkcji, zapoznaj się z [Zarządzanie funkcjami — omówienie](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Wszystkie nowe funkcje pozostają w podglądzie przez co najmniej 30 dni, a zazwyczaj 30-60 dni. Najważniejsze funkcje są zazwyczaj dostępne w październiku i kwietniu każdego roku po okresie podglądu. Po wyświetleniu nowych możliwości w obszarze roboczym **zarządzanie funkcjami** można je włączyć. Niektóre funkcje mogą być domyślnie włączone.

Gdy funkcja jest ogólnie dostępna, może być włączana lub wyłączana w środowiskach produkcyjnych. Przestrzeń robocza **Zarządzanie funkcjami** wskazuje, kiedy funkcja podglądu stanie się obowiązkowa. Ta data zazwyczaj jest równa 1 października lub 1 kwietnia w celu dostosowania ich do półrocznych planów zwolnień. Nie można wyłączać obowiązkowych funkcji. Dopóki ta funkcja nie stanie się obowiązkowa, można ją włączać i wyłączać we wszystkich środowiskach.

## <a name="enable-or-disable-preview-features"></a>Włączanie i wyłączanie funkcji zapoznawczych

Aby uzyskać dostęp do funkcji w wersji zapoznawczej, należy je najpierw włączyć w środowisku. Włączanie lub wyłączanie funkcji zapoznawczych jest specyficzne dla środowiska.

> [!IMPORTANT]
> Funkcje w wersji zapoznawczej będą włączone tylko w środowiskach **Piaskownica**. Włączenie ustawienia funkcji w wersji zapoznawczej skutkuje włączeniem funkcji w wersji zapoznawczej wszystkim użytkownikom w organizacji pracującym w tym środowisku. Wyłączenie ustawienia funkcji zapoznawczej powoduje jej wyłączenie i zablokowanie użytkownikom dostępu do niej. Funkcje zapoznawcze otrzymują wsparcie tylko w ograniczonym zakresie w aplikacji Human Resources. Mogą korzystać ze mniejszej ilości narzędzi ochrony prywatności i bezpieczeństwa oraz nie są objęte umową dotyczącą poziomu usług (SLA) zawieraną dla aplikacji HUman Resources. Nie należy używać funkcji zapoznawczych do przetwarzania danych osobowych (tzn. wszelkich informacji, które mogą jednoznacznie identyfikować użytkownika) ani innych danych, które podlegają prawnym lub ustawowym wymogom dotyczącym zgodności.

1. W module Human Resources wybierz opcję **administrowanie systemem**.

2. Wybierz kafelek **Zarządzanie funkcjami**.

3. Aby włączyć funkcję podglądu, wybierz ją z listy, a następnie wybierz opcję **Włącz**. Aby wyłączyć funkcję podglądu, wybierz ją z listy, a następnie wybierz opcję **Wyłącz**.

## <a name="preview-feature-benefits-management"></a>Funkcja w wersji zapoznawczej: Zarządzanie świadczeniami

Zarządzanie świadczeniami zapewnia elastyczne rozwiązanie, które obsługuje wiele różnych opcji świadczeń oraz łatwe w użyciu doświadczenie zawodowe, które przedstawia Twoją ofertę. Aby uzyskać więcej informacji na temat konfiguracji i użytkowania funkcji [Zarządzanie świadczeniami - omówienie](hr-benefits-management-overview.md).

Zarządzanie świadczeniamii zastępuje funkcje w obszarze roboczym **Świadczenia**. Po włączeniu funkcji Zarządzanie świadczeniami, nie można już uzyskać dostępu do następujących formularzy w obszarze roboczym **Świadczenia:**

- **Świadczenia**
- **Elementy świadczenia**
- **Stawki obliczania udziału**
- **Wynik zapisywania na świadczenia**
- **Wyniki wygaszania i rozszerzania świadczeń**
- **Typy reguł uprawnień do świadczenia**
- **Zasady uprawnień do świadczeń**
- **Zdarzenia dotyczące uprawnień**

Informacje zawarte w tych formularzach można przeglądać w trybie tylko do odczytu. Jeśli chcesz edytować te informacje, musisz najpierw wyłączyć funkcję Podgląd korzyści do zarządzania.

### <a name="benefits-management-known-issues"></a>Znane problemy związane z zarządzaniem korzyściami

#### <a name="life-events"></a>Zdarzenia zmiany sytuacji życiowej

Podczas przetwarzania zdarzeń dotyczących okresu istnienia użytkownika zostanie zgłoszony błąd:

Data początkowa zapotrzebowania musi być między *początkiem okresu planu* a *końcem okresu planu*. 

Zdarzenie dotyczące okresu istnienia będzie nadal przetwarzane zgodnie z oczekiwaniami.

#### <a name="eligibility-processing"></a>Przetwarzanie uprawnień

Podczas używania uprawnień do świadczeń wykorzystujących ustawienia kwoty ubezpieczenia 1-5 X wynagrodzenie, % wynagrodzenia lub Równa kwota, należy w obszarze **Historia zatrudnienia** w ustawieniu pracownika podać wartość daty rozpoczęcia świadczenia dla pracownika, podając godziny pracy, jak często wypłacane jest świadczenie oraz roczne zestawienie świadczeń do pensji. Jeśli dla pracownika istnieje stała kompensacja, wprowadź liczbę godzin przepracowanych wraz z częstotliwością płatności, a następnie obliczy roczną kwotę zarobków. Jeśli pracownik otrzymuje wynagrodzenie za etat, nie trzeba wypełniać pola przepracowane godziny. Zaleca się, aby podczas tworzenia nowych pracowników najpierw wprowadzić stałe wynagrodzenie. Aby zaktualizować rekord szczegółów świadczenia, wybierz opcje **Pracownik > Historia pracownika > Szczegóły zatrudnienia**. Skoryguj datę na datę rozpoczęcia zatrudnienia pracownika.

#### <a name="employee-self-service"></a>Samoobsługa pracownika

Pracownicy mogą wybrać plan, do którego nie mają kwalifikacji i zatwierdzić go. Na przykład: pracownik nie ma żadnych osób zależnych, ale może wybrać plan medyczny z opcją pokrycia rodzinnego.

Kwota pracownika nie jest obliczana w przypadku aktualizacji kwoty ubezpieczenia na życie. Jeśli na przykład pracownikowi zostanie zaoferowany plan ubezpieczenia na życie, może on wybrać do 50 000 USD w ramach kosztu wynoszącego 0,36 USD za 1000 USD zwrotu.  Gdy pracownik aktualizuje kwotę zapotrzebowania, koszt przypisany do pracownika pozostanie równy zero.

W przypadku planu świadczeń, który zezwala tylko na jednokrotnie wybranie tego typu planu, użytkownik zobaczy błąd, jeśli zechce zrezygnować z planu po jego wybraniu. Na przykład użytkownik wybiera plan medyczny i umieszcza go w swoim koszyku. Następnie użytkownik wybiera **Zrzeczenie się** innego planu medycznego. Zostanie zwrócony błąd użytkownika.

## <a name="preview-features-in-leave-and-absence"></a>Podgląd funkcji urlopu i nieobecności

Podgląd funkcji urlopu i nieobecności to m.in.:

- **Kalendarz urlopów i nieobecności** — urlop i parametry nieobecności będą przenoszone z parametrów modułu **Human Resources** do nowego ekranu o nazwie **Urlop i nieobecność**. Nowy ekran zawiera nową kartę **Kalendarz**. Ten podgląd umożliwia tylko wgląd w podzestaw parametrów. Nowy ekran można uzyskać, korzystając z karty **Łącza** w obszarze roboczym **urlop i nieobecność**. Do kalendarzy należy:
  - **Kalendarz firmy** — umożliwia wyświetlenie wszystkich żądań wyłączenia czasu pracy pracownika. Osoby z rolą **Human Resources** mogą uzyskać dostęp do tego kalendarza z karty **Łącza** w obszarze roboczym **Urlop i nieobecność**.
  - **Kalendarz zespołu Menedżera** — umożliwia wyświetlenie wszystkich żądań czasu wolnego. Menedżerowie mogą uzyskać dostęp do kalendarza z karty **Mój zespół** w module Samoobsługa pracownika w ramach funkcji **urlop i nieobecność**. 

- **Urlopy i kalendarze - świąteczne nieobecności** — typy urlopów zawierają nową opcję **Urlop świąteczny**, używaną w połączeniu z kalendarzem czasu pracy. Dni określone przez dni wolne i zamknięcia są obecnie wyznaczone jako **Święta** w przypadku generowania dni roboczych. Podczas przetwarzania naliczeń są wprowadzane poprawki - pracownicy przypisani są do kalendarza w celu uwzględnienia świąt przypadających w dniu pracy.

- **Dane dot. urlopu** — nowy ekran umożliwia przeglądanie, kiedy naliczenia zostały przetworzone i usunięte, zarówno przez pracowników, jak i poszczególnych pracowników. Ten nowy ekran można uzyskać, korzystając z karty **Łącza** w obszarze roboczym **Urlop i nieobecność**.

- **Usunięcie danych dot. urlopu** — teraz możesz usunąć rekordy naliczania dla konkretnych planów urlopów. Tę nową opcję można uzyskać, korzystając z karty **Łącza** w obszarze roboczym **Urlop i nieobecność**. W przypadku poszczególnych pracowników ta opcja jest wyświetlana w grupie **Urlop i nieobecność** w profilu pracownika. 

- **Zaokrąglanie danych dot urlopu** — nowe opcje dla **Typu urlopu** umożliwiają zdefiniowanie zaokrąglania, powiększonej o precyzję dziesiętną zaokrąglenia w procesie naliczania. Podczas przetwarzania naliczeń w rekordach naliczania są stosowane zaokrąglenie i precyzja. 

- **Konfigurowanie wielu typów urlopu dla jednego planu** — nowa kolumna w harmonogramie wystawiania urlopów dla typów urlopów umożliwia zdefiniowanie wielu typów urlopów w przypadku urlopu i nieobecności z różnymi harmonogramami naliczania. Pole poprzedniego **Typu urlopu** jest usunięte. Przy zarejestrowaniu pracownika, salda dla typów urlopu są teraz wyświetlane w tabeli, a nie w górnej części ekranu.

  > [!IMPORTANT]
  > Po włączeniu tej funkcji nie można jej wyłączyć.

- **Użycie ekwiwalentu pełnego etatu pracownika etatowego (FTE) w celu naliczenia** — nowa kolumna w harmonogramie naliczania urlopu umożliwia używanie pełnego ekwiwalentu FTE do naliczania. Podczas przetwarzania naliczeń aplikacja używa podstawowego stanowiska pracownika oraz pełnego etatu zdefiniowanego w celu określenia proporcjonalnej kwoty naliczania.

  > [!NOTE]
  > Ta funkcja jest dostępna tylko po włączeniu opcji **Skonfiguruj wiele typów urlopu dla jednego planu urlopu**. 

## <a name="feedback"></a>Opinii

Chcemy się dowiedzieć, co sądzisz, na podstawie swojego doświadczenia, o tych funkcjach w wersji zapoznawczej. Zachęcamy do regularnego zamieszczania opinii w podanych witrynach podczas korzystania z tych i innych funkcji:

- [Społeczność](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) — Ta witryna to doskonała platforma, na której użytkownicy mogą omawiać scenariusze zastosowania, zadawać pytania i otrzymywać osób od podobnych im osób.
- Opowiedz nam o funkcjach, które Twoim zdaniem powinny się znaleźć w produkcie, a także o wszelkich zmianach, które Twoim zdaniem należy wprowadzić w istniejących funkcjach. Sugeruj pomysły dotyczące produktów [Human Resources](https://powerusers.microsoft.com/t5/Ideas-for-Human-Resources/idb-p/HumanResources)
    
W przesyłanych opiniach i recenzjach produktu nie podawaj żadnych danych osobowych (tzn. informacji, które mogłyby Cię identyfikować). Zebrane informacje mogą być dalej analizowane, ale ze względu na obowiązujące przepisy o ochronie danych osobowych nie będą wykorzystywane do udzielania odpowiedzi na pytania. Dane osobowe, które na mocy tych programów są zbierane osobno, podlegają [zasadom zachowania poufności informacji firmy Microsoft](https://privacy.microsoft.com/privacystatement).

## <a name="see-also"></a>Informacje dodatkowe

- [Co nowego: Human Resources](hr-admin-whats-new.md)
- [Plan wydawniczy rozwiązań Dynamics 365 i Power Platform](https://docs.microsoft.com/dynamics365/release-plans/#pivot=products&panel=products1)