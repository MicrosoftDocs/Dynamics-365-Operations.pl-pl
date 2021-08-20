---
title: Jednostki skalowania chmury i urządzenia brzegowego dla obciążeń pracą dotyczących produkcji i zarządzania magazynem
description: Ten temat przedstawia informacje na temat zarządzania jednostką skali chmury i urządzenia brzegowego przy produkcji i wykonywaniu zadań magazynowych.
author: cabeln
ms.date: 04/22/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: cabeln
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: dbe5833d4c9d8038fcebf1d9d446af757c834e42a2f77f10c7eb7268e738ed28
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6780681"
---
# <a name="cloud-and-edge-scale-units-for-manufacturing-and-warehouse-management-workloads"></a>Jednostki skalowania chmury i urządzenia brzegowego dla obciążeń pracą dotyczących produkcji i zarządzania magazynem

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> Możliwość jednostki skali dla Microsoft Dynamics 365 Dynamics 365 Supply Chain Management jest udostępniana użytkownikowi na warunkach regulujących korzystanie z usługi. Aby uzyskać więcej informacji, zobacz [Informacje prawne Microsoft Dynamics](https://go.microsoft.com/fwlink/?LinkID=290927).
>
> Włączając jednostki skali chmury i krawędzi, należy pamiętać, że musisz potwierdzić, że pewne dane związane z konfiguracją i przetwarzaniem jednostek skali granicznej mogą być przechowywane w centrum danych znajdującym się w Stanach Zjednoczonych. Aby dowiedzieć się więcej o przetwarzaniu danych w chmurze i jednostek skali urządzenia brzegowego, zobacz sekcję [Przetwarzanie danych podczas zarządzania jednostkami skali](#data-processing-management) w dalszej części tego tematu.

## <a name="core-value-proposition-for-scale-units"></a>Propozycja wartości podstawowej dla jednostek skali

Firmy pracujące z produkcją i dystrybucją muszą mieć możliwość uruchamiania podstawowych procesów biznesowych 24/7, bez przerw i w skali. Jednostki skali chmury i urządzenia brzegowego umożliwiają firmom uruchamianie kluczowych procesów produkcyjnych i magazynowych, nawet w obliczu przerwanej łączności sieciowej lub opóźnienia.

Jednostki skali chmury i urządzenia brzegowego umożliwiają dystrybucję obciążenia pracą produkcyjną i wykonaniem magazynów w różnych środowiskach. Ta funkcja może ułatwić poprawę wydajności, zapobiegać przerwom w świadczeniu usług oraz maksymalizuje czas pracy. Jednostki skali są dostarczane za pośrednictwem następujących dodatków do subskrypcji Supply Chain Management:

- Dodatek jednostki skali w chmurze Dynamics 365 Supply Chain Management (*dostępne od kwietnia 2021*)
- Dodatek jednostki skali na krawędzi w chmurze Dynamics 365 Supply Chain Management (*dostępne wkrótce*)

Możliwości obciążenia są udostępniane w sposób ciągły poprzez stopniowe ulepszenia.

## <a name="scale-units-and-dedicated-workloads"></a>Jednostki skali i wydzielone obciążenie pracą

Jednostki skali rozszerzają centralne środowisko centrum Supply Chain Management przez dodanie dedykowanych zdolności produkcyjnych. Jednostki skalowania mogą być uruchamiane w chmurze. Alternatywnie mogą działać na obrzeżach, lokalnie w lokalnym zakładzie.

:::image type="content" source="./media/cloud_edge-HeroDiagram.png" alt-text="Dynamics 365 z jednostkami skali.":::

Jednostki skali zapewniają odporność, niezawodność i skalowalność dla przypisanych obciążeń. Jednostki skali na krawędzi można tymczasowo odłączyć od środowiska centrum chmury, a pracownicy nadal pracują w przypisanych obciążeniach na krawędzi.

*Obciążenie* pracą jest zdefiniowanym zestawem funkcji biznesowych, który może być rozważony i delegowany do jednostki skalowania. Chociaż obciążenie związane z zarządzaniem magazynem zostało zwolnione, obciążenie związane z wykonywaniem produkcji jest nadal dostępne w wersji zapoznawczej.

Można skonfigurować środowisko centrum i jednostki skalowania w chmurze dla wybranych obciążeń, korzystając z [portalu Menedżera jednostki skalowania](https://sum.dynamics.com).. Możesz również przypisać wiele obciążeń na jednostkę skali. Aby uzyskać informacje o wymaganiach wstępnych i ograniczeniach dotyczących jednostek skalowania w chmurze w bieżącej wersji, zobacz sekcję [Wymagania wstępne i ograniczenia dotyczące jednostek skalowania w chmurze](#cloud-scale-unit-prerequisites) w dalszej części tematu.

### <a name="dedicated-warehouse-management-workload-capabilities-in-a-scale-unit"></a>Dedykowane możliwości zarządzania pracą magazynową w jednostce skalowania

Obciążenie zarządzania magazynem jest pierwszym rozproszonym obciążeniem dla jednostek skalowania, które zostało udostępnione do ogólnej dostępności.

W przypadku zarządzania magazynem jednostki wagowe zapewniają następujące możliwości:

- System może przetwarzać wybrane metody fal dla zleceń sprzedaży i uzupełniania zapasów.
- Pracownicy magazynu mogą uruchamiać pracę magazynową sprzedaży i uzupełnienia popytu, korzystając z aplikacji Warehouse Management.
- Pracownicy magazynu mogą uzyskiwać dostęp do dostępnych zapasów za pośrednictwem aplikacji Warehouse Management.
- Pracownicy magazynu mogą tworzyć i uruchamiać przesunięcia zapasów za pośrednictwem aplikacji Warehouse Management.
- Pracownicy magazynu mogą rejestrować zamówienia zakupu i wykonywać odłożenia pracy przy użyciu aplikacji Warehouse Management.

Aby uzyskać więcej informacji, zobacz temat [Obciążenia pracą dotyczące zarządzania magazynem dla jednostek skalowania chmury i urządzenia brzegowego](cloud-edge-workload-warehousing.md).

### <a name="dedicated-manufacturing-execution-workload-capabilities-in-a-scale-unit"></a>Dedykowane możliwości wykonywania produkcyjnych w jednostkach skali

Pierwsza wersja obciążenia produkcyjnego jest obecnie w wersji zapoznawczej i zapewnia następujące możliwości:

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

Dane przesyłane i przechowywane w centrach danych w USA zostaną usunięte zgodnie z zasadami przechowywania danych firmy Microsoft. Twoja prywatność jest ważna dla Microsoft. Więcej informacji na ten temat znajduje się w [zasadach zachowania poufności informacji ](https://go.microsoft.com/fwlink/?LinkId=521839).

## <a name="onboarding-in-two-stages"></a>Dołączanie w dwóch etapach

Proces dołączania do rozproszonej topologii hybrydowej składa się z dwóch etapów. Na pierwszym etapie należy sprawdzić poprawność dostosowań, aby upewnić się, że działają one w topologii rozproszonej z jednostkami skalowania. Środowiska sandbox i produkcyjne są przenoszone dopiero w drugim etapie.

### <a name="stage-1-evaluate-customizations-in-one-box-development-environments"></a>Etap 1: ocena dostosowań w jedno-pudełkowych środowiskach programistycznych

Zanim zaczniesz wdrażać swoje piaskownice lub środowiska produkcyjne, zalecamy zbadanie jednostek skalowania w konfiguracji programistycznej, takiej jak środowisko typu one-box (znane również jako środowisko warstwy 1), aby można było weryfikować procesy, dostosowania, i rozwiązania. Na tym etapie dane i dostosowania zostaną zastosowane w środowiskach typu „one-box”. Jedno środowisko pełni rolę centrum, a drugie jednostki skali. Te ustawienia zapewniają najlepszą identyfikację i rozwiązywanie problemów. Do ukończenia tego etapu można również użyć najnowszej kompilacji wczesnego dostępu (PEAP).

W przypadku etapu 1 należy używać [narzędzi wdrażania jednostek skalowania w środowiskach programistycznych o jednym polu](https://github.com/microsoft/SCMScaleUnitDevTools). Te narzędzia umożliwiają konfigurowanie centrów i jednostek skalowania w jednym lub dwóch oddzielnych środowiskach typu one-box. Narzędzia są dostarczane w wersji binarnej oraz w kodzie źródłowym w serwisie GitHub. Przejmij stronę typu wiki projektu, która zawiera [Przewodnik krok po kroku](https://github.com/microsoft/SCMScaleUnitDevTools/wiki/Step-by-step-usage-guide), w którym opisano sposób korzystania z tych narzędzi.

### <a name="stage-2-acquire-add-ins-and-deploy-in-your-sandbox-and-production-environments"></a>Etap 2: Nabywanie dodatków oraz wdrażanie w piaskownicy i środowiskach produkcyjnych

Aby dołączyć jedno ze swoich środowisk piaskownicy lub środowisk produkcyjnych do nowej topologii, należy nabyć dodatki dla co najmniej jednej jednostki skalowania w chmurze (a w przyszłości - dla jednostek skalowania brzegowego). Dodatki przyznają odpowiednie miejsca na projekty i środowiska w [LCS](https://lcs.dynamics.com/), aby można było wdrożyć środowiska jednostek skalowania.

> [!NOTE]
> Dodatki jednostek skalowania nie są połączone z ograniczoną liczbą użytkowników, ale mogą być używane przez dowolnego użytkownika w istniejącej subskrypcji na podstawie ról przypisanych przez administratora.

Jednostki wagowe są oferowane w wielu jednostkach magazynowych (SKU) i opcjach cenowych. Dlatego możesz wybrać opcję, która najlepiej odpowiada planowanej miesięcznej liczbie transakcji i wymaganiom dotyczącym wydajności.

Podstawowa jednostka SKU jest znana jako *Podstawowa*, a bardziej wydajna jednostka SKU jest znana jako *Standardowa*. Każdy SKU jest wstępnie załadowany określoną liczbą miesięcznych transakcji. Możesz jednak zwiększyć miesięczny budżet transakcji, dodając dodatki nadwyżkowe dla każdej jednostki SKU.

:::image type="content" source="media/SKUs-highlevel.png" alt-text="Dodatki dla jednostek skalowania w chmurze.":::

> [!TIP]
> Aby określić rozmiar, który najlepiej odpowiada Twoim potrzebom, we współpracy z partnerem i firmą Microsoft ustal wielkość wymaganej miesięcznej transakcji.

Zakup każdego dodatku jednostki skali nie tylko zapewnia miesięczną liczbę transakcji, ale także uprawnia do określonej liczby miejsc w środowisku w LCS. Za każdy dodatek Jednostki skalowania w chmurze masz prawo do jednego nowego miejsca produkcyjnego i jednego nowego miejsca w piaskownicy. Podczas procesu wdrażania zostanie dodany nowy projekt LCS, który ma te miejsca. Prawa użytkowania dla gniazd są powiązane, więc gniazda muszą być używane jako jednostki skalowania, które mają centrum w chmurze.

Dodatki nadwyżkowe nie uprawniają do nowych miejsc w środowisku.

Jeśli chcesz zdobyć więcej środowisk piaskownicy, możesz kupić dodatkowe zwykłe miejsca w piaskownicy. Firma Microsoft pomoże włączyć te gniazda jako jednostki skalowania piaskownicy dla topologii hybrydowej.

## <a name="onboard-to-the-distributed-hybrid-topology-for-supply-chain-management"></a>Wbudowany w rozproszoną, hybrydową topologię do Supply Chain Management

### <a name="select-your-lcs-project-tenant-and-the-detailed-onboarding-process"></a>Wybierz dzierżawę projektu usługi LCS i szczegółowy proces dołączania

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

### <a name="manage-cloud-scale-units-and-workloads-by-using-the-scale-unit-manager-portal"></a><a name="scale-unit-manager-portal"></a>Zarządzanie jednostkami i obciążeniem skali chmury przy użyciu portalu Menedżera jednostki skalowania

Przejdź do [portalu Menedżera jednostki skalowania ](https://aka.ms/SCMSUM)i zaloguj się przy użyciu konta dzierżawy. Na **stronie Konfigurowanie jednostek skali** można dodać środowisko centralne, jeśli nie jest jeszcze umieszczone na liście. Następnie można wybrać centrum, które ma zostać skonfigurowane przy użyciu jednostek skali i obciążeń.

:::image type="content" source="media/cloud_edge-Manage.png" alt-text="Obsługa jednostki skalowania i zarządzanie obciążeniem — doświadczenie.":::

Aby dodać jedną lub więcej jednostek skali, które są dostępne w subskrypcjach, wybierz opcję **Dodaj jednostki skalowania**.

Na **karcie zdefiniowane obciążenia**, za pomocą przycisku **Utwórz obciążenie pracą** można dodać obciążenie zarządzania magazynem do jednej z jednostek skali. Dla każdego obciążenia należy określić kontekst procesów, które będą należały do obciążenia pracą. W przypadku obciążeń zarządzania magazynem kontekst jest określonym magazynem w określonym oddziale i firmie.

:::image type="content" source="media/cloud_edge-DefineWorkload.png" alt-text="Tworzenie obciążenia pracą.":::

> [!TIP]
> Z biegiem czasu do środowiska Menedżer jednostek skalowania będą dodawane stopniowe ulepszenia, aby ułatwić operacje zarządzania cyklem życia. Specyficzne możliwości dla bieżącej wersji są udokumentowane w podręczniku wprowadzającym, który jest dostępny dla klientów, którzy są w trakcie wdrażania do rozproszonej, hybrydowej topologii Supply Chain Management. <!-- KFM: Add a link to the handbook when it is published -->

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
