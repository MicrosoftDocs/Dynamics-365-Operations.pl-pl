---
title: Jednostki skalowania w dystrybuowanej topologii hybrydowej
description: Ten artykuł przedstawia informacje na temat zarządzania jednostką skali chmury i urządzenia brzegowego przy produkcji i wykonywaniu zadań magazynowych.
author: Mirzaab
ms.date: 04/22/2021
ms.topic: article
ms.search.form: ScaleUnitWorkloadsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6b53822238220ccfcf538d49285e051c49c57189
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8893679"
---
# <a name="scale-units-in-a-distributed-hybrid-topology"></a>Jednostki skalowania w dystrybuowanej topologii hybrydowej

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> Możliwość jednostki skali dla Microsoft Dynamics 365 Dynamics 365 Supply Chain Management jest udostępniana użytkownikowi na warunkach regulujących korzystanie z usługi. Aby uzyskać więcej informacji, zobacz [Informacje prawne Microsoft Dynamics](https://go.microsoft.com/fwlink/?LinkID=290927).
>
> Włączając jednostki skali chmury i krawędzi, należy pamiętać, że musisz potwierdzić, że pewne dane związane z konfiguracją i przetwarzaniem jednostek skali granicznej mogą być przechowywane w centrum danych znajdującym się w Stanach Zjednoczonych. Aby dowiedzieć się więcej o przetwarzaniu danych w chmurze i jednostek skali urządzenia brzegowego, zobacz sekcję [Przetwarzanie danych podczas zarządzania jednostkami skali](#data-processing-management) w dalszej części tego artykułu.

## <a name="core-value-proposition-for-a-distributed-hybrid-topology"></a>Propozycja wartości podstawowej dla dystrybuowanej topologii hybrydowej

Firmy pracujące z produkcją i dystrybucją muszą mieć możliwość uruchamiania podstawowych procesów biznesowych 24/7, bez przerw i w skali. Dystrybuowana topologia hybrydowa umożliwia firmom uruchamianie kluczowych procesów produkcyjnych i magazynowych, nawet w obliczu przerwanej łączności sieciowej lub opóźnienia.

Dystrybuowana topologia hybrydowa wprowadza pojęcie *jednostek skalowania*, które umożliwiają rozkład obciążenia pracą produkcji i wykonywania w magazynie w różnych środowiskach. Ta funkcja może ułatwić poprawę wydajności, zapobiegać przerwom w świadczeniu usług oraz maksymalizuje czas pracy. Jednostki skali są dostarczane za pośrednictwem następujących dodatków do subskrypcji Supply Chain Management:

- Dodatek jednostki skali chmury dla Dynamics 365 Supply Chain Management
- Dodatek jednostki skali urządzenia brzegowego dla Dynamics 365 Supply Chain Management

Możliwości obciążenia są udostępniane w sposób ciągły poprzez stopniowe ulepszenia.

## <a name="scale-units-and-dedicated-workloads"></a>Jednostki skali i wydzielone obciążenie pracą

Jednostki skali rozszerzają centralne środowisko centrum Supply Chain Management przez dodanie dedykowanych zdolności produkcyjnych. Jednostki skalowania mogą być uruchamiane w chmurze. Alternatywnie mogą działać na [obrzeżach](cloud-edge-edge-scale-units-lbd.md), lokalnie w lokalnym zakładzie.

:::image type="content" source="./media/cloud_edge-HeroDiagram.png" alt-text="Dynamics 365 z jednostkami skali.":::

Jednostki skali zapewniają odporność, niezawodność i skalowalność dla przypisanych obciążeń. Jednostki skali na krawędzi można tymczasowo odłączyć od środowiska centrum chmury, a pracownicy nadal pracują w przypisanych obciążeniach na krawędzi.

*Obciążenie* pracą jest zdefiniowanym zestawem funkcji biznesowych, który może być rozważony i delegowany do jednostki skalowania. Chociaż obciążenie związane z zarządzaniem magazynem zostało zwolnione, obciążenie związane z wykonywaniem produkcji jest nadal dostępne w wersji zapoznawczej.

Można skonfigurować środowisko centrum i jednostki skalowania w chmurze dla wybranych obciążeń, korzystając z [portalu Menedżera jednostki skalowania](https://sum.dynamics.com).. Możesz również przypisać wiele obciążeń na jednostkę skali. Aby uzyskać informacje o wymaganiach wstępnych i ograniczeniach dotyczących jednostek skalowania w chmurze w bieżącej wersji, zobacz sekcję [Wymagania wstępne i ograniczenia dotyczące jednostek skalowania w chmurze](#cloud-scale-unit-prerequisites) w dalszej części artykułu.

### <a name="dedicated-warehouse-management-workload-capabilities-in-a-scale-unit"></a>Dedykowane możliwości zarządzania pracą magazynową w jednostce skalowania

Obciążenie związane z zarządzaniem magazynem umożliwia skalowanie i uruchamianie operacji magazynowych w elastycznym środowisku za pomocą izolowanych okien konserwacji. Praca związana z zarządzaniem magazynem wspiera większość procesów zarządzania magazynem w centrum przedsiębiorstwa. Aby uzyskać więcej informacji, zobacz temat [Obciążenia pracą dotyczące zarządzania magazynem dla jednostek skalowania chmury i urządzenia brzegowego](cloud-edge-workload-warehousing.md).

### <a name="dedicated-manufacturing-execution-workload-capabilities-in-a-scale-unit"></a>Dedykowane możliwości wykonywania produkcyjnych w jednostkach skali

Obciążenie pracą produkcji oferuje następujące możliwości:

- Operatorzy maszyn i kierownicy mogą uzyskać dostęp do operacyjnego planu produkcji.
- Operatorzy maszynowi mogą regularnie aktualizować plan, uruchamiając dyskretne i przetwarzające zadania produkcyjne.
- Kierownik produkcji może skorygować plan operacyjny.
- Pracownicy mogą uzyskać dostęp do modułu czas i frekwencja do zarejestrowania i wyrejestrowania się na brzegu, aby zapewnić poprawne Obliczanie wynagrodzeń pracowników.

Aby uzyskać więcej informacji, zobacz temat [Obciążenia wykonywania produkcji dla jednostek skalowania w chmurze i na urządzeniach brzegowych](cloud-edge-workload-manufacturing.md).

## <a name="considerations-before-you-enable-the-distributed-hybrid-topology-for-supply-chain-management"></a>Uwagi przed włączeniem dystrybuowanej, topologii hybrydowej dla Supply Chain Management

Włączając rozproszoną topologię hybrydową, przenosisz środowisko chmurowe Supply Chain Management, tak aby działało jako centrum. Możesz również skojarzyć dodatkowe środowiska, które są skonfigurowane jako jednostki skalowania w chmurze lub na krawędzi.

### <a name="prerequisites-and-limitations-for-cloud-scale-units"></a><a name="cloud-scale-unit-prerequisites"></a>Wymagania wstępne i ograniczenia dotyczące jednostek skalowania w chmurze

W bieżącej wersji dla jednostek skalowania niektóre funkcje nie są jeszcze dostępne, ale mogą być dodawane w kolejnych wersjach w miarę upływu czasu.

#### <a name="you-must-be-a-licensed-customer-of-supply-chain-management"></a>Musisz być licencjonowanym klientem Supply Chain Management

Aby dołączyć do topologii rozproszonej, musisz mieć licencję na Supply Chain Management. Twoje istniejące środowisko chmurowe stanie się centrum Twojej topologii hybrydowej. Możesz zadeklarować zarówno środowiska piaskownicy, jak i środowiska produkcyjne jako środowiska centralne, a także możesz dodawać jednostki skalowania zgodnie z nabytymi dodatkami.

#### <a name="your-existing-project-must-be-administered-via-the-global-commercial-version-of-lcs"></a>Twój istniejący projekt musi być administrowany za pośrednictwem globalnej komercyjnej wersji LCS

Twój istniejący projekt Microsoft Dynamics Lifecycle Services (LCS) musi spełniać następujące wymagania dotyczące wersji:

- Projekt musi być administrowany za pośrednictwem globalnej komercyjnej wersji LCS pod adresem [lcs.dynamics.com](https://lcs.dynamics.com).
- Wersje lokalne usługi LCS (takie jak [eu.lcs.dynamics.com](https://eu.lcs.dynamics.com) i [fr.lcs.dynamics.com](https://fr.lcs.dynamics.com)) nie są obsługiwane.
- Wersje usługi LCS w chmurze rządowej nie są obsługiwane.
- Wersja Mooncake usługi LCS nie jest obsługiwana.

#### <a name="your-current-production-environment-must-be-of-the-self-service-type-in-lcs"></a>Twoje bieżące środowisko produkcyjne musi być typu samoobsługowego w LCS

Twoje obecne środowisko produkcyjne musi być oznaczone typem **Samoobsługa** w LCS. Ten typ wskazuje, że dzierżawca projektu LCS został już przekonwertowany, tak aby obsługiwał model hostingu Azure Service Fabric.

> [!IMPORTANT]
> Typy środowisk, które działają jako infrastruktura jako usługa (IaaS), nie są obsługiwane. Te środowiska są zwykle oznaczone typem **Zarządzane przez firmę Microsoft** w LCS. Jeśli masz środowiska tego typu, skontaktuj się z osobą kontaktową w firmie Microsoft, aby poznać harmonogram migracji do typu **Samoobsługa**.

Firma Microsoft jest w trakcie przenoszenia wszystkich środowisk chmurowych rozwiązania Supply Chain Management z modelu IaaS do topologii hostowanej w Service Fabric. To posunięcie zapewnia lepszą skalowalność i ułatwia zarządzanie usługami. Dlatego operacje wdrażania i konserwacji są szybsze. Podobnie składniki usług są migrowane do koncepcji mikrousług, a model hostingu usług [przejdzie](/virtualization/windowscontainers/about/containers-vs-vm) z modelu maszyny wirtualnej (VM) do lekkiej architektury kontenerowej.

Ostatecznie ta sama konteneryzowana infrastruktura usług oparta na Service Fabric będzie obsługiwać zarówno wystąpienia usługi w chmurze, jak i skrajne, niezależnie od tego, czy wystąpienie jest centrum w chmurze, czy też jednostką skalowania w chmurze lub na brzegu.

Zanim będzie można dołączyć do topologii hybrydowej, która obsługuje jednostki skalowania, dzierżawca projektu musi zostać przeniesiony do modelu hostowanego w Service Fabric. Ponadto każde środowisko, które będzie działać jako centrum, musi zostać przekonwertowane.

> [!TIP]
> Aby zapytać o stan dzierżawy projektu LCS, wyszukaj typ swojego środowiska w [LCS](https://lcs.dynamics.com/) lub skontaktuj się z partnerem lub osobą kontaktową firmy Microsoft.

#### <a name="local-business-data-on-premises-environments-arent-supported-as-hubs-for-scale-units"></a>Lokalne środowiska danych biznesowych (lokalne) nie są obsługiwane jako centra dla jednostek skalowania

Środowiska lokalne nie mogą działać jako centra dla jednostek skalowania. Środowiska koncentratora muszą zawsze być hostowane w chmurze.

#### <a name="scale-unit-management-capabilities-are-limited"></a>Możliwości zarządzania jednostkami wagi są ograniczone

Możliwości zarządzania, które mogą pomóc w przenoszeniu obciążeń, są ograniczone. Niektóre operacje zarządzania nie są obsługiwane w sposób samoobsługowy i może być konieczne poproszenie o pomoc techniczną za pośrednictwem partnera lub osoby kontaktowej firmy Microsoft. Przykłady obejmują pewne przesunięcia obciążenia między jednostkami skalowania i tymczasowe ruchy ad hoc w scenariuszach katastrof.

#### <a name="metrics-and-measurements-arent-yet-available"></a>Metryki i miary nie są jeszcze dostępne

Metryki i miary, które mogą pomóc w wyborze najlepszej aplikacji dla jednostek skali, nie są jeszcze dostępne. Skontaktuj się z osobą kontaktową firmy Microsoft lub partnerem wdrożeniowym, aby wybrać najkorzystniejszą aplikację.

### <a name="data-processing-during-management-of-scale-units"></a><a name="data-processing-management"></a>Przetwarzanie danych podczas zarządzania jednostkami skali

Gdy włączysz środowisko Dynamics 365 do obsługi rozproszonej, hybrydowej topologii dla jednostek chmurowych i jednostek skali brzegowej, niektóre usługi zarządzania będą hostowane tylko w Stanach Zjednoczonych, tak jak w przypadku LCS. To zachowanie wpływa na przesyłanie i przechowywanie niektórych informacji administracyjnych i konfiguracyjnych, które są używane przez [portal Menedżer jednostek skalowania](https://sum.dynamics.com). Oto kilka przykładów:

- Nazwy i identyfikatory dzierżaw
- Twój identyfikator projektu LCS
- Adresy e-mail administratora i właściciela projektu, które są używane do logowania
- Identyfikatory środowiska dla jednostki centrum i skali
- Konfiguracje obciążeń, w tym nazwy i adresy fizyczne podmiotów prawnych i obiektów, aby Twoja topologia mogła być pokazana na mapie geograficznej
- Zebrane metryki (takie jak opóźnienie i przepustowość), które będą wyświetlane na stronie analizy mapy, aby pomóc Ci wybrać najbardziej korzystne wykorzystanie jednostek skali

Dane przesyłane i przechowywane w centrach danych w USA zostaną usunięte zgodnie z zasadami przechowywania danych firmy Microsoft. Twoja prywatność jest ważna dla Microsoft. Więcej informacji na ten temat znajduje się w [Oświadczeniu o ochronie prywatności](https://go.microsoft.com/fwlink/?LinkId=521839).

## <a name="onboard-to-the-distributed-hybrid-topology-for-supply-chain-management"></a>Wbudowany w rozproszoną, hybrydową topologię do Supply Chain Management

### <a name="try-out-the-distributed-hybrid-topology"></a>Wypróbuj rozproszoną topologię hybrydową

Proces dołączania do rozproszonej topologii hybrydowej składa się z dwóch etapów. Na pierwszym etapie należy [wypróbować](cloud-edge-try-out.md) rozwiązanie i zweryfikować dostosowania, aby upewnić się, że działają w rozproszonej topologii obejmującej jednostki skali. (Do walidacji można użyć istniejących środowisk programistycznych). Następnie można przejść do drugiego etapu, w którym nabywa się środowiska produkcyjne.

## <a name="select-your-lcs-project-tenant-and-the-detailed-onboarding-process"></a>Wybierz dzierżawę projektu usługi LCS i szczegółowy proces dołączania

Jednostki wagowe są oferowane w wielu jednostkach magazynowych (SKU) i opcjach cenowych. Dlatego możesz wybrać opcję, która najlepiej odpowiada planowanej miesięcznej liczbie transakcji i wymaganiom dotyczącym wydajności.

> [!TIP]
> Aby określić rozmiar, który najlepiej odpowiada Twoim potrzebom, współpracuj z partnerem wdrożeniowym i firmą Microsoft, aby poznać wymagany miesięczny rozmiar transakcji.

Podstawowa jednostka SKU jest znana jako *Podstawowa*, a bardziej wydajna jednostka SKU jest znana jako *Standardowa*. Każdy SKU jest wstępnie załadowany określoną liczbą miesięcznych transakcji. Możesz jednak zwiększyć miesięczny budżet transakcji, dodając dodatki nadwyżkowe dla każdej jednostki SKU.

:::image type="content" source="media/SKUs-highlevel.png" alt-text="Dodatki dla jednostek skalowania w chmurze.":::

> [!NOTE]
> Dodatki jednostek skalowania nie są połączone z ograniczoną liczbą użytkowników. Są one dostępne dla każdego użytkownika w ramach istniejącej subskrypcji (pod warunkiem, że administrator przypisał im wymagane role użytkownika).

Zakup każdego dodatku jednostki skali nie tylko zapewnia miesięczną liczbę transakcji, ale także uprawnia do określonej liczby miejsc w środowisku w LCS. Za każdy dodatek Jednostki skalowania w chmurze masz prawo do jednego nowego miejsca produkcyjnego i jednego nowego miejsca w piaskownicy. Podczas procesu wdrażania zostanie dodany nowy projekt LCS, który ma te miejsca. Prawa użytkowania dla gniazd są powiązane, więc gniazda muszą być używane jako jednostki skalowania, które mają centrum w chmurze.

Dodatki nadwyżkowe nie uprawniają do nowych miejsc w środowisku.

Jeśli chcesz zdobyć więcej środowisk piaskownicy, możesz kupić dodatkowe zwykłe miejsca w piaskownicy. Firma Microsoft pomoże włączyć te gniazda jako jednostki skalowania piaskownicy dla topologii hybrydowej.


Po zakończeniu planowania sposobu dołączania do rozproszonej, hybrydowej topologii Supply Chain Management, będziesz korzystać z [portalu menedżera jednostek skalowania](https://aka.ms/SCMSUM), aby rozpocząć proces wdrażania. W portalu wybierz kartę **Dynamics 365 Tenants**. Ta karta jest wyświetlana lista dzierżawców, do których należy konto, oraz miejsce, w którym użytkownik jest administratorem projektu usługi LCS.

Jeśli poszukiwany dzierżawca nie znajduje się na liście, przejdź do [usługi LCS ](https://lcs.dynamics.com/v2)i upewnij się, że jesteś administratorem środowiska lub właścicielem projektu usługi LCS dla tego dzierżawcy. Tylko Azure Active Directory(Azure AD) konta z wybranej dzierżawy są upoważnione do ukończenia korzystania z funkcji zapisywania się.

> [!NOTE]
> Po zastosowaniu zmian w LCS lista dzierżawców może zająć do 30 minut, zanim zmiany zostaną odzwierciedlone.

Dla każdej dzierżawy na liście jest wyświetlany stan dołączania.

:::image type="content" source="media/cloud_edge-EnableHybrid1.png" alt-text="Lista dzierżawców na karcie Dynamics 365 Tenants.":::

Wybierz pozycję **Kliknij tutaj, aby rozpocząć** dołączanie żądań dla dzierżawy usługi LCS. Musisz zaakceptować warunki. Należy również podać firmowy adres e-mail, pod którym firma Microsoft może wysłać komunikację powiązaną z procesem dołączania.

:::image type="content" source="media/cloud_edge-EnableHybrid2.png" alt-text="Rejestracja zgłoszenia w celu uzyskania subskrypcji w wersji zapoznawczej dla dzierżawcy.":::

Firma Microsoft sprawdzi Twoją prośbę i poinformuje o następnych krokach, wysyłając wiadomość e-mail na adres podany w formularzu zapisywania się. Firma Microsoft będzie ściśle z Tobą współpracować, aby włączyć jednostki skalowania w topologii hybrydowej dla Twojego scenariusza biznesowego.

Po zakończeniu dołączania można użyć portu do skonfigurowania jednostek skalowania i obciążeń.

### <a name="manage-scale-units-and-workloads-by-using-the-scale-unit-manager-portal"></a><a name="scale-unit-manager-portal"></a>Zarządzanie jednostkami i obciążeniem skali przy użyciu portalu Menedżera jednostki skalowania

Przejdź do [portalu Menedżera jednostki skalowania ](https://aka.ms/SCMSUM)i zaloguj się przy użyciu konta dzierżawy. Na **stronie Konfigurowanie jednostek skali** można dodać środowisko centralne, jeśli nie jest jeszcze umieszczone na liście. Następnie można wybrać centrum, które ma zostać skonfigurowane przy użyciu jednostek skali i obciążeń.

:::image type="content" source="media/cloud_edge-Manage.png" alt-text="Portal Menedżera jednostek skalowania, konfiguracja strony jednostek skali.":::

Aby dodać jedną lub więcej jednostek skali, które są dostępne w subskrypcjach, wybierz opcję **Dodaj jednostki skalowania**.

Na **karcie zdefiniowane obciążenia**, za pomocą przycisku **Utwórz obciążenie pracą** można dodać obciążenie zarządzania magazynem do jednej z jednostek skali. Dla każdego obciążenia należy określić kontekst procesów, które będą należały do obciążenia pracą. W przypadku obciążeń zarządzania magazynem kontekst jest określonym magazynem w określonym oddziale i firmie.

:::image type="content" source="media/cloud_edge-DefineWorkload.png" alt-text="Definiowanie okna dialogowego obciążenia pracą.":::

#### <a name="manage-workloads"></a><a name="manage-workloads"></a>Zarządzanie obciążeniami pracą

Po włączeniu jednego lub większej liczby obciążenia pracą użyj opcji **Zarządzaj obciążeniami**, aby zainicjować procesy, takie jak wymienione w poniższej tabeli, i zarządzać nimi.

| Przetwarzaj | Opis |
|---|---|
| Wstrzymywanie komunikacji jednostek skalowania | Wstrzymywanie komunikatów potoku między centrum a jednostką skali. Ten proces spowoduje zatrzymanie komunikacji i opróżnienie potoku danych między centrum a jednostkami skalowania. Ten proces należy uruchomić przed uruchomieniem operacji obsługi Supply Chain Management dla centrum lub jednostki skalowania, ale można jej użyć także w innych sytuacjach. |
| Wznów komunikację z wagą | Wznów komunikaty potoku między centrum a jednostką skalowania. Może być konieczne użycie tego procesu, na przykład po uruchomieniu operacji obsługi Supply Chain Management dla centrum lub jednostki skalowania. |
| Uaktualnij obciążenia | Synchronizuj nową funkcjonalność między obciążeniami centrum i jednostki skalowania. Może być konieczne użycie tego procesu, na przykład, jeśli obsługa spowodowała zmianę kwerend wymiany danych i/lub dodano nowe tabele lub pola do obciążenia pracą. |
| Przenoszenie obciążenia pracą do jednostki skali | Zaplanuj obciążenie pracą, które jest obecnie uruchomione w centrum, aby zostać przeniesione do jednostki skalowania. Po uruchomieniu tego procesu będzie przepływać synchronizacja danych, a centrum i jednostka skali zostaną ustawione tak, aby zmieniły prawa własności obciążenia pracą. |
| Przenieś jednostkę wagi do piasty | Zaplanuj obciążenie, które jest aktualnie uruchomione w jednostce skalowania, które ma zostać przeniesione do centrum. Po uruchomieniu tego procesu będzie przepływać synchronizacja danych, a centrum i jednostka skali zostaną ustawione tak, aby zmieniły prawa własności obciążenia pracą.
| Przejście alarmowe do centrum | <p>Natychmiast przenieś istniejące obciążenie pracą do centrum. *Ten proces spowoduje zmianę prawa własności tylko do danych, które są obecnie dostępne w centrum.*</p><p><strong>Ostrzeżenie:</strong> Ten proces może spowodować utratę danych przez niezsynchronizowane dane i niepowodzenie przetwarzania biznesowego. Dlatego należy go używać tylko w procesach biznesowych, w których należy przetwarzać procesy biznesowe w centrum, ponieważ w jednostce skalowania znajduje się okres, którego nie można minimaliować w odpowiednim czasie.</p> |
| Rozproszona topologia likwidacji | Usuń wdrożenie jednostki skalowania i uruchom tylko w centrum bez przetwarzania obciążenia pracą. |

:::image type="content" source="media/sum-manage-workloads.png" alt-text="Obsługa jednostki skalowania i zarządzanie obciążeniem — doświadczenie.":::

> [!TIP]
> Z biegiem czasu do środowiska Menedżer jednostek skalowania będą dodawane stopniowe ulepszenia, aby ułatwić operacje zarządzania cyklem życia. Specyficzne możliwości dla bieżącej wersji są udokumentowane w podręczniku wprowadzającym, który jest dostępny dla klientów, którzy są w trakcie wdrażania do rozproszonej, hybrydowej topologii Supply Chain Management. <!-- KFM: Add a link to the handbook when it is published -->

## <a name="feature-management-considerations-for-workloads"></a>Zagadnienia związane z zarządzaniem funkcjami dla obciążenia pracą

Ta sekcja zawiera informacje o kilku istotnych aspektach, które należy uwzględnić podczas instalowania obciążenia pracą, dodawania funkcji lub usuwania funkcji w dystrybuowanej topologii hybrydowej. Kilka scenariuszy może mieć wpływ na to, czy po wprowadzeniu zmian konieczne będzie uruchomienie [aktualizacji obciążenia](#manage-workloads). Zazwyczaj jest to jednak wymagane podczas aktualizowania lub dodawania nowych kwerend wymiany danych i/lub dodawania nowych tabel lub pól do poprzednio zainstalowanego obciążenia pracą.

### <a name="mandatory-features-for-installing-a-workload"></a>Wymagane funkcje instalowania obciążenia pracą

Podczas instalowania obciążenia pracą proces instalacji tworzy definicję obciążenia pracą zawierającą informacje o tabelach danych używanych podczas synchronizacji danych między tymi dwoma wdrożeniami. Tworzenie definicji obciążenia pracą jest obsługiwane automatycznie na podstawie funkcji, które są obecnie włączone w [zarządzaniu funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). W poniższej tabeli wymieniono funkcje, które muszą być włączone, aby można było generować definicje obciążenia pracą wymagane do uruchomienia obciążenia pracą magazynu lub produkcji.

| Funkcja obowiązkowa | Obciążenie |
|---|---|
| Automatyczne przypisywanie identyfikatorów GUID przy tworzeniu użytkownika WHS | Magazyn |
| Blokowanie pracy na poziomie organizacji | Magazyn |
| Szczegóły etykiety grupy czynności wysyłki | Magazyn |
| Obsługa jednostki skalowania dla list pracy aplikacji magazynowej | Magazyn |
| Wykonanie hali produkcyjnej | Produkcja |

Podczas wdrażania obciążenia przy użyciu [narzędzi do wdrażania jednostek skalowania dla jednoelementowych środowisk programistycznych](https://github.com/microsoft/SCMScaleUnitDevTools) lub [portalu menedżera jednostek skalowania](https://sum.dynamics.com) wszystkie obowiązkowe funkcje zostaną automatycznie włączone. Jeśli jednak wykonasz ręczne wdrożenie testowe, w którym brakuje co najmniej jednej obowiązkowej funkcji, instalacja obciążenia zakończy się niepowodzeniem i otrzymasz komunikat z listą brakujących funkcji. Następnie należy ręcznie włączyć te funkcje i ponownie uruchomić instalację obciążenia pracą.

### <a name="enabling-or-disabling-features-that-have-data-synchronization-dependencies"></a>Włączanie lub wyłączanie funkcji, które mają zależności synchronizacji danych

Funkcje wpływające na wybór danych synchronizowanych między centrum a jego jednostkami skalowania mają również wpływ na sposób tworzenia definicji obciążenia. Dlatego ważne jest, aby te funkcje były włączone przed zainstalowaniem obciążenia pracą. Jeśli włączysz ten typ funkcji podczas wykonywania obciążenia, musisz ponownie wygenerować definicję obciążenia, uruchamiając [uaktualnienie obciążenia](#manage-workloads) po włączeniu tej funkcji. Podobnie, jeśli wyłączysz funkcję, która jest uzależniona od synchronizacji danych podczas uruchamiania obciążenia, musisz uruchomić [uaktualnienie obciążenia](#manage-workloads), aby usunąć odpowiednie informacje o synchronizacji danych z definicji obciążenia.

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
