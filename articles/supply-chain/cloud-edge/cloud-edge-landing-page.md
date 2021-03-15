---
title: Jednostki skalowania chmury i urządzenia brzegowego dla obciążeń pracą dotyczących produkcji i zarządzania magazynem
description: Ten temat przedstawia informacje na temat zarządzania jednostką skali chmury i urządzenia brzegowego przy produkcji i wykonywaniu zadań magazynowych.
author: cabeln
manager: ''
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: cabeln
ms.search.validFrom: 2020-09-23
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 28301cdfb86d00ea6f04e996fe7fb1485e83b2d4
ms.sourcegitcommit: 289e9183d908825f4c8dcf85d9affd4119238d0c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104971"
---
# <a name="cloud-and-edge-scale-units-for-manufacturing-and-warehouse-management-workloads"></a>Jednostki skalowania chmury i urządzenia brzegowego dla obciążeń pracą dotyczących produkcji i zarządzania magazynem

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Jednostki skali chmury i urządzenia brzegowego umożliwiają dystrybucję obciążenia pracą produkcyjną i wykonaniem magazynów w różnych środowiskach. Ta funkcja może ułatwić poprawę wydajności, zapobiegać przerwom w świadczeniu usług oraz maksymalizuje czas pracy. Jest on dostarczany przez następujące dodatki:

- Dodatek jednostki skali chmury dla Dynamics 365 Supply Chain Management
- Dodatek jednostki skali urządzenia brzegowego dla Dynamics 365 Supply Chain Management

Firmy pracujące z produkcją i dystrybucją muszą mieć możliwość uruchamiania podstawowych procesów biznesowych 24/7, bez przerw i w skali. Jednostki skali chmury i urządzenia brzegowego umożliwiają firmom uruchamianie kluczowych procesów produkcyjnych i magazynowych, nawet w obliczu przerwanej łączności sieciowej lub opóźnienia.

## <a name="public-preview-information"></a>Informacje o publicznej wersji zapoznawczej

Podgląd zapewnia jedno środowisko, które działa jako centralne centrum Dynamics 365 Supply Chain Managementśrodowiska i jedno środowisko działające jako jednostka skali chmury.

<!-- You will also be able to use Local Business Data (LBD) to configure an on-premises environment as an edge scale unit for the hub you received as part of the preview program.-->

### <a name="preview-availability"></a>Dostępność wersji zapoznawczej

Podgląd dla jednostek skali w chmurze i urządzeń brzegowych jest dostępny dla istniejących odbiorców modułu Zarządzanie łańcuchem dostaw w październiku 2020.

Aby uzyskać dostęp do październikowej wersji zapoznawczej 10.0.15/platform update 39 w celu wdrożenia w środowisku [Microsoft Dynamics Lifecycle Services (usługi LCS)](https://lcs.dynamics.com/v2), musisz należeć do programu wczesnego dostępu PEAP dla Supply Chain Management. Można dołączyć protokół PEAP, jeśli jesteś już członkiem szerszego programu [Dynamics Insider Program](https://experience.dynamics.com/insider). Wybierz tylko określony program o nazwie „operacje finansowe &: podgląd wersji programu Access (PEAP)”

> [!IMPORTANT]
> Możliwość tworzenia jednostek skali w Supply Chain Management jest dostępna tylko wtedy, gdy użytkownik zgodzi się na warunki [wersji zapoznawczej Cloud + Edge dla Finance and Operations](https://Aka.ms/SCMCnETerms).

### <a name="data-processing-for-the-preview"></a>Przetwarzanie danych dla podglądu

W podglądzie publicznym niektóre usługi zarządzania będą przechowywane tylko w Stanach Zjednoczonych. Jeśli jednak funkcja jest ogólnie dostępna, te usługi zarządzania będą dostępne we wszystkich lokalizacjach obsługiwanych przez Supply Chain Management. Ma to wpływ na transfer i przechowywanie informacji administracyjnych używanych przez Menedżera jednostki skalowania, w tym:

- Nazwy i identyfikatory dzierżaw
- Twój identyfikator projektu LCS
- Adresy e-mail administratora służące do logowania
- Identyfikatory środowiska dla jednostki centrum i skali
- Konfiguracje obciążenia
- Zebrane metryki (takie jak czas oczekiwania i przepływność) wyświetlane na stronie analizy mapy

Dane przenoszone do i przechowywane w Stanach Zjednoczonych centra danych zostaną usunięte po zamknięciu środowiska podglądu.

### <a name="sign-up-for-the-preview"></a>Rejestracja w celu uzyskania wersji zapoznawczej

Aby zarejestrować się w chmurze i podglądzie Supply Chain Management, Twoja organizacja musi mieć już środowisko chmurowe Supply Chain Management.

Możliwości jednostki skalowania są obecnie w publicznej wersji Preview. Podczas rejestrowania się należy skorzystać z konta użytkownika w określonym dzierżawie. Ponadto użytkownik musi być właścicielem projektu lub administratorem środowiska w usługi LCS dla aktywnego projektu usługi LCS systemu Dynamics 365 w tym dzierżawie.

Po zapisaniu się w celu uzyskania podglądu wybierzesz dzierżawcę i przejdziesz przez kroki rejestracji. Gdy tylko firma Microsoft będzie mogła przydzielić dyspozycyjność w wersji Preview, wyśle do Ciebie wiadomość e-mail zawierającą szczegóły dotyczące zainicjowania obsługi oraz kody promocji środowisk (centrum i jednostki skali) dla odpowiedniego projektu usługi LCS. Można wówczas wdrożyć te dwa środowiska jako środowiska testowe warstwy 2. Te środowiska będą obowiązywać 60 dni od daty utworzenia kodów promocyjnych. Nie należy używać tych dwóch środowisk, dopóki nie zostanie ukończony krok opisany w następnym akapicie.

Po potwierdzeniu firmie Microsoft, że te dwa środowiska zostały wdrożone za pomocą kodów awansowania, jedno z środowisk zostanie skonfigurowane do pracy jako centrum, a drugi zostanie skonfigurowany do pracy jako jednostka skali. Następnie można skonfigurować jednostki skali i wdrożyć wybrane obciążenia magazynowe i obciążenie pracą przy użyciu [modułu Menedżer jednostki skali](https://aka.ms/SCMSUM).

Środowisko podglądu zostanie automatycznie usunięte po 60 dniach. Mogą jednak zostać usunięte wcześniej, jeśli okaże się, że nie są używane. Po usunięciu środowisk podglądu można utworzyć konto i kolejno w kolejce, aby utworzyć nowe wdrożenie w wersji Preview.

Aby zarejestrować się w celu uzyskania podglądu, przejdź do [portalu Menedżera jednostki skalowania](https://aka.ms/SCMSUM).

### <a name="limitations-that-apply-during-the-preview-period"></a>Ograniczenia, które obowiązują w okresie podglądu

> [!IMPORTANT]
> W przypadku początkowej fazy programu podglądu dla tej funkcji firma Microsoft obsługuje tylko te koncentratory, które mają jednostki skalowania w chmurze, a nie koncentratory o jednostce skali krawędzi. Jednostki skali krawędzi są instalowane lokalnie i oczekuje się, że będą dostępne podczas nadchodzącej fazy programu.

Ponieważ jednostki skali chmury i krawędzi są funkcją podglądu, związane z nimi usługi są obecnie dostępne w ograniczonych krajach i regionach. Włączając jednostki skali chmury i krawędzi, należy pamiętać, że pewne dane związane z konfiguracją i przetwarzaniem jednostek skali granicznej mogą być przechowywane w centrum danych znajdującym się w Stanach Zjednoczonych. Włączenie jednostek skali w chmurze i krawędzi powoduje również zgodę na [warunki wersji zapoznawczej Finance and Operations dla chmury i Edge](https://Aka.ms/SCMCnETerms). Aby dowiedzieć się więcej o jednostkach chmury i brzegowej, zapoznaj się z [dokumentacją ](https://aka.ms/scmcne).

Twoja prywatność jest ważna dla Microsoft. Więcej informacji na ten temat znajduje się w [zasadach zachowania poufności informacji ](https://aka.ms/privacy).

> [!IMPORTANT]
> Nie wszystkie funkcje biznesowe są w pełni obsługiwane w podglądzie publicznym, gdy są obciążenia są używane dla jednostki skali. Aby uzyskać więcej informacji na temat obciążeń funkcjonalnych, zobacz opisy parametrów w dalszej części tego tematu.

## <a name="scale-units-and-dedicated-workloads"></a>Jednostki skali i wydzielone obciążenie pracą

:::image type="content" source="./media/cloud_edge-HeroDiagram.png" alt-text="Dynamics 365 z jednostkami skali":::

Jednostki skali rozszerzają centralne środowisko centrum Supply Chain Management przez dodanie dedykowanych zdolności produkcyjnych. Jednostki skalowania mogą być uruchamiane w chmurze. Można je również uruchamiać na krawędziach w lokalnych lokalach instrumentu. Jednostki skalowania mogą być tymczasowo odłączone od środowiska centrum. Po podłączeniu jednostki skalowania uzyskują wszystkie informacje wymagane do uruchomienia dedykowanego przetwarzania przydzielonych obciążeń.

:::image type="content" source="media/cloud_edge-previewoptions.png" alt-text="Opcje skalowania jednostki w podglądzie publicznym":::

W przypadku wersji zapoznawczej można skonfigurować środowisko centralne z wybranymi obciążeniami w jednostce skali chmury, korzystając z portalu Menedżera jednostki skalowania. Uczestnicy wersji zapoznawczej, którzy mają dostęp do lokalnych danych biznesowych (LBD) w środowisku lokalnym, mogą również skonfigurować środowisko LBD jako jednostkę skali krawędzi.

Obciążenie pracą jest zdefiniowanym zestawem funkcji biznesowych, który może być rozważony i delegowany do jednostki skalowania. Obecnie w podglądzie są wymienione dwa typy obciążeń:

- Wykonywanie produkcji
- Zarządzanie magazynem

Można przypisać jeden z każdego typu obciążenia na jednostkę skali. 

### <a name="dedicated-manufacturing-execution-workload-capabilities-in-a-scale-unit"></a>Dedykowane możliwości wykonywania produkcyjnych w jednostkach skali

W module Uruchomienie produkcji jednostki skali chmury i urządzenia brzegowego zapewniają następujące możliwości, nawet jeśli jednostki brzegowe nie są połączone z chmurą:

- Operatorzy maszyn i kierownicy mogą uzyskać dostęp do operacyjnego planu produkcji.
- Operatorzy maszynowi mogą regularnie aktualizować plan, uruchamiając dyskretne i przetwarzające zadania produkcyjne.
- Kierownik produkcji może skorygować plan operacyjny.
- Pracownicy mogą uzyskać dostęp do modułu czas i frekwencja do zarejestrowania i wyrejestrowania się na brzegu, aby zapewnić poprawne Obliczanie wynagrodzeń pracowników.

Aby uzyskać więcej informacji, zajrzyj do [szczegółów obciążenia pracą jednostki skali](cloud-edge-workload-manufacturing.md).

### <a name="dedicated-warehouse-management-workload-capabilities-in-a-scale-unit"></a>Dedykowane możliwości zarządzania pracą magazynową w jednostce skalowania

Przy zarządzaniu magazynem w jednostki skali chmury i urządzenia brzegowego zapewniają następujące możliwości, nawet jeśli jednostki brzegowe nie są połączone z centrum:

- Przetwarzanie wybranych metod grupy czynności jest włączone dla zamówień sprzedaży i uzupełniania popytu.
- Pracownicy magazynu mogą uruchamiać pracę magazynową sprzedaży i uzupełnienia popytu, korzystając z aplikacji magazynowej.
- Pracownicy magazynu mogą uzyskiwać dostęp do dostępnych zapasów za pośrednictwem aplikacji magazynu.
- Pracownicy magazynu mogą tworzyć i uruchamiać przesunięcia zapasów za pośrednictwem aplikacji magazynu.
- Pracownicy magazynu mogą rejestrować zamówienia zakupu i wykonywać odłożenia pracy przy użyciu aplikacji magazynowej

Aby uzyskać więcej informacji, zajrzyj do [szczegółów obciążenia pracą jednostki skali w magazynie](cloud-edge-workload-warehousing.md).

## <a name="onboard-scale-units-for-your-supply-chain-management-environment"></a>Wdrażanie jednostki skali dla środowiska Supply Chain Management

### <a name="deploy-the-preview-for-cloud-and-edge-scale-units"></a>Uruchomienie wersji zapoznawczej dla jednostek skalowania chmury i urządzenia brzegowego

Na poniższej ilustracji przedstawiono przepływ zapisywania i tworzenia zainicjowania obsługi dla jednostki skalowania w chmurze w wersji zapoznawczej.

:::image type="content" source="media/cloud_edge-previewsignup.png" alt-text="Kroki rejestracji dla wesji zapoznawczej":::

### <a name="select-your-lcs-project-tenant-and-the-detailed-preview-process"></a>Wybierz dzierżawę projektu usługi LCS i szczegółowy proces wersji zapoznawczej

W wersji zapoznawczej [portalu Menedżera jednostki skalowania](https://aka.ms/SCMSUM) jest wyświetlana lista dzierżawców, do których należy konto, oraz miejsce, w którym użytkownik jest administratorem projektu usługi LCS.

Jeśli poszukiwany dzierżawca nie znajduje się na liście, przejdź do [usługi LCS ](https://lcs.dynamics.com/v2)i upewnij się, że jesteś administratorem środowiska lub właścicielem projektu usługi LCS dla tego dzierżawcy. Należy zauważyć, że tylko Azure Active Directory(Azure AD) konta z wybranej dzierżawy są upoważnione do ukończenia korzystania z funkcji zapisywania się.

> [!NOTE]
> Po zastosowaniu zmian w usługi LCS może upłynąć do 30 minut w celu odzwierciedlenia zmian w liście dzierżawców.

Dla każdej dzierżawy na liście jest wyświetlany stan zapisywania się.

:::image type="content" source="media/cloud_edge-Signup1.png" alt-text="Rejestracja w celu uzyskania subskrypcji w wersji zapoznawczej dla dzierżawcy":::

Wybierz łącze **Kliknij, aby się zarejestrować** w celu zarejestrowania Twojej dzierżawy usługi LCS w celu uczestnictwa w wersji Preview. Musisz zaakceptować warunki. Należy również podać firmowy adres e-mail, pod którym firma Microsoft może wysłać komunikację powiązaną z procesem zapisywania się w wersji Preview.

:::image type="content" source="media/cloud_edge-Signup2.png" alt-text="Rejestracja zgłoszenia w celu uzyskania subskrypcji w wersji zapoznawczej dla dzierżawcy":::

Firma Microsoft sprawdzi Twoją prośbę i poinformuje o następnych krokach, wysyłając wiadomość e-mail na adres podany w formularzu zapisywania się.

Po przyznaniu dostępu do programu podglądu, dla projektu usługi LCS zostaną wyświetlone dwa kody promocyjne. Teraz można stosować kody promocyjne do wdrażania dwóch środowisk w usługi LCS. W środowiskach musi być używany protokół PEAP 10.0.15 Release lub nowszy. Po zakończeniu stosowania kodów awansowania należy powiadomić firmę Microsoft (zgodnie z instrukcjami), aby umożliwić nam zakończenie włączania środowisk dla funkcji podglądu. Firma Microsoft informuje o zakończeniu tego kroku konfiguracji systemu.

Teraz można rozpocząć konfigurowanie jednostek skali i obciążeń w środowisku podglądu.

> [!IMPORTANT]
> Konfigurując jednostki skalowania w chmurze, można [wykonać wszystkie wymagane kroki w portalu Menedżera jednostki skalowania](#scale-unit-manager-portal).
<!-- 
> If want to use edge scale units with your preview deployment, you must do all scale unit configuration in the user interface on the hub as described in [Configure the hub environment for use with edge scale units](cloud-edge-edge-scale-units-lbd.md#configure-the-hub-environment). You can't use Scale Unit Manager portal if you include an edge scale unit. -->

### <a name="manage-cloud-scale-units-and-workloads-by-using-the-scale-unit-manager-portal"></a><a name="scale-unit-manager-portal"></a>Zarządzanie jednostkami i obciążeniem skali chmury przy użyciu portalu Menedżera jednostki skalowania

Przejdź do [portalu Menedżera jednostki skalowania ](https://aka.ms/SCMSUM)i zaloguj się przy użyciu konta dzierżawy. Na **stronie Konfigurowanie jednostek skali** można dodać środowisko centralne, jeśli nie jest jeszcze umieszczone na liście. Następnie można wybrać centrum, które ma zostać skonfigurowane przy użyciu jednostek skali i obciążeń.

:::image type="content" source="media/cloud_edge-Manage.png" alt-text="Obsługa jednostki skalowania i zarządzanie obciążeniem — doświadczenie":::

Aby dodać jedną lub więcej jednostek skali, które są dostępne w topologii, wybierz opcję **Dodaj jednostki skalowania**. W podglądzie powinna zostać wyświetlona jednostka skali chmury, która została wdrożona z jednego z kodów promocyjnych, który został przyjęty jako część programu podglądu.

<!--  [!IMPORTANT]
> In the public preview, the Scale Unit Manager portal shows the cloud scale unit that you received as part of the preview program. Any edge scale unit that you created based on an LBD configuration can't be managed in the Scale Unit Manager portal yet. For configuration details, see [Deploy custom edge scale units on custom hardware using LBD](cloud-edge-edge-scale-units-lbd.md) -->

Na **karcie zdefiniowane obciążenia**, za pomocą przycisku **Utwórz obciążenie pracą** można dodać magazyn lub obciążenie pracą produkcyjną do jednej z jednostek skali. Dla każdego obciążenia należy określić kontekst procesów, które będą należały do obciążenia pracą. W przypadku obciążeń zarządzania magazynem kontekst jest określonym magazynem w określonym oddziale i firmie. W przypadku obciążeń pracą dotyczącą produkcji, kontekst jest określonym oddziałem w firmie.

:::image type="content" source="media/cloud_edge-DefineWorkload.png" alt-text="Tworzenie obciążenia pracą":::

> [!IMPORTANT]
> Portal Menedżera jednostki skalowania w podglądzie nie umożliwia usuwania obciążenia z jednostek skali lub cofania przypisania jednostki skali od koncentratora po wykonaniu przydziału. Jeśli trzeba usunąć przypisanie, należy skontaktować się z osobą kontaktową w celu uzyskania podglądu programu.

<!-- ### Create an edge scale unit using your custom on-premises hardware appliance

In the public preview, you can create on-premises edge scale units on your custom hardware using the LBD environments. For details, see [Deploy custom edge scale units on custom hardware using LBD](cloud-edge-edge-scale-units-lbd.md). -->


[!INCLUDE[footer-include](../../includes/footer-banner.md)]