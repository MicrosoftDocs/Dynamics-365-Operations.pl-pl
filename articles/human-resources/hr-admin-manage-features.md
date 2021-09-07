---
title: Zarządzanie funkcjami w module Zasoby ludzkie
description: W tym temacie opisano funkcję zarządzania funkcjami i sposób jego używania.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 61e40f7177a1c8cf3d60a9a991ecbb0ed4d93aa1
ms.sourcegitcommit: 72a82e9aeabbdecf57e1aee72975c63eba75143a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/24/2021
ms.locfileid: "7414640"
---
# <a name="manage-features-in-human-resources"></a>Zarządzanie funkcjami w module Zasoby ludzkie

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W ramach ciągłego wdrażania nowych funkcji zarządzania w aplikacji Microsoft Dynamics 365 Human Resources chcemy stworzyć klientom możliwość jak najszybszego zetknięcia się z nimi. Te funkcje są dostępne gdyż są prawie gotowe do ogólnego udostępnienia i przeszły wszechstronne testy. Jednak zanim je upublicznimy powszechnie, chcemy jeszcze poznać finalne opinie klientów i przeprowadzić ostatnią weryfikację.

Aby uzyskać więcej informacji o nowych funkcjach w aplikacji Human Resources, zobacz [Nowości i zmiany w aplikacji Human Resources](hr-admin-whats-new.md) oraz [Informacje o planie wydawniczym Dynamics 365 i Power Platform](/dynamics365/release-plans/?panel=products1#pivot=products).

Obszar roboczy **zarządzanie funkcjami** zawiera listę funkcji dostarczanych w każdym wydaniu. Domyślnie nowe funkcje są wyłączone. Można użyć obszaru roboczego, aby włączyć je i wyświetlić dokumentację dla nich. Aby uzyskać więcej informacji o zarządzaniu funkcjami funkcji, zapoznaj się z [Zarządzanie funkcjami — omówienie](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Wszystkie nowe funkcje pozostają w podglądzie przez co najmniej 30 dni, a zazwyczaj 30-60 dni. Najważniejsze funkcje są zazwyczaj dostępne w październiku i kwietniu każdego roku po okresie podglądu. Po wyświetleniu nowych możliwości w obszarze roboczym **zarządzanie funkcjami** można je włączyć. Niektóre funkcje mogą być domyślnie włączone.

Gdy funkcja jest ogólnie dostępna, może być włączana lub wyłączana w środowiskach produkcyjnych. Przestrzeń robocza **Zarządzanie funkcjami** wskazuje, kiedy funkcja podglądu stanie się obowiązkowa. Ta data zazwyczaj jest równa 1 października lub 1 kwietnia w celu dostosowania ich do półrocznych planów zwolnień. Nie można wyłączać obowiązkowych funkcji. Dopóki ta funkcja nie stanie się obowiązkowa, można ją włączać i wyłączać we wszystkich środowiskach.

## <a name="enable-or-disable-preview-features"></a>Włączanie i wyłączanie funkcji zapoznawczych

Aby uzyskać dostęp do funkcji w wersji zapoznawczej, należy je najpierw włączyć w środowisku. Włączanie lub wyłączanie funkcji zapoznawczych jest specyficzne dla środowiska.

> [!IMPORTANT]
> Funkcje w wersji zapoznawczej będą włączone tylko w środowiskach **Piaskownica**. Włączenie ustawienia funkcji w wersji zapoznawczej skutkuje włączeniem funkcji w wersji zapoznawczej wszystkim użytkownikom w organizacji pracującym w tym środowisku. Wyłączenie ustawienia funkcji zapoznawczej powoduje jej wyłączenie i zablokowanie użytkownikom dostępu do niej. Funkcje zapoznawcze otrzymują wsparcie tylko w ograniczonym zakresie w aplikacji Human Resources. Mogą korzystać ze mniejszej ilości narzędzi ochrony prywatności i bezpieczeństwa oraz nie są objęte umową dotyczącą poziomu usług (SLA) zawieraną dla aplikacji HUman Resources. Nie należy używać funkcji zapoznawczych do przetwarzania danych osobowych (tzn. wszelkich informacji, które mogą jednoznacznie identyfikować użytkownika) ani innych danych, które podlegają prawnym lub ustawowym wymogom dotyczącym zgodności.

1. W module Human Resources wybierz opcję **administrowanie systemem**.

2. Wybierz kafelek **Zarządzanie funkcjami**.

3. Aby włączyć funkcję podglądu, wybierz ją z listy, a następnie wybierz opcję **Włącz**. Aby wyłączyć funkcję podglądu, wybierz ją z listy, a następnie wybierz opcję **Wyłącz**.

## <a name="enable-or-disable-benefits-management"></a>Włączanie lub wyłączanie obszaru roboczego Zarządzanie świadczeniami

Aby włączyć zarządzanie świadczeniami, należy zastosować tę samą procedurę w funkcjach [Włączanie i wyłączanie funkcji zapoznawczych](hr-admin-manage-features.md?enable-or-disable-preview-features).

> [!IMPORTANT]
> Nie można wyłączyć zarządzania świadczeniami w środowisku **Produkcyjnym** po jego włączeniu. Można jednak wyłączyć funkcję zarządzania świadczeniami w środowiskach **Piaskownicy**.

Aby uzyskać więcej informacji na temat konfiguracji i użytkowania funkcji [Zarządzanie świadczeniami - omówienie](hr-benefits-management-overview.md).

Zarządzanie świadczeniamii zastępuje funkcje w obszarze roboczym **Świadczenia**. Po włączeniu funkcji Zarządzanie świadczeniami, nie można już uzyskać dostępu do następujących formularzy w obszarze roboczym **Świadczenia:**

- **Świadczenia**
- **Elementy świadczenia**
- **Stawki obliczania udziału**
- **Wynik zapisywania na świadczenia**
- **Wyniki wygaszania i rozszerzania świadczeń**
- **Typy reguł uprawnień do świadczenia**
- **Zasady uprawnień do świadczeń**
- **Zdarzenia dotyczące uprawnień**

Informacje zawarte na tych stronach można przeglądać w trybie tylko do odczytu. Jeśli chcesz edytować te informacje, musisz najpierw wyłączyć funkcję Zarządzania świadczeniami (dotyczy tylko środowisk **Piaskownicy**).

## <a name="enable-or-disable-leave-and-absence"></a>Włączanie lub wyłączanie urlopu i nieobecności

Aby włączyć Urlopy i nieobecności, należy zastosować tę samą procedurę w funkcjach [Włączanie i wyłączanie funkcji zapoznawczych](hr-admin-manage-features.md?enable-or-disable-preview-features).

> [!IMPORTANT]
> Nie można wyłączyć funkcji **Wiele typów urlopów** w Urlopy i nieobecności po jej włączeniu. Dotyczy to zarówno środowisk **Piaskownicy**, jak i **Produkcyjnych**.

Aby uzyskać więcej informacji o funkcjach w wersji zapoznawczej dotyczących Urlopów i nieobecności, zobacz [Funkcje w wersji zapoznawczej dotyczące urlopów i nieobecności](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

## <a name="send-us-feedback"></a>Wyślij nam opinię

Chcemy się dowiedzieć, co sądzisz, na podstawie swojego doświadczenia, o tych funkcjach w wersji zapoznawczej. Zachęcamy do regularnego zamieszczania opinii w podanych witrynach podczas korzystania z tych i innych funkcji:

- [Społeczność](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) — Ta witryna to doskonała platforma, na której użytkownicy mogą omawiać scenariusze zastosowania, zadawać pytania i otrzymywać osób od podobnych im osób.
- Opowiedz nam o funkcjach, które Twoim zdaniem powinny się znaleźć w produkcie, a także o wszelkich zmianach, które Twoim zdaniem należy wprowadzić w istniejących funkcjach. Sugeruj pomysły dotyczące produktów na stronie [pomysły Human Resources](https://powerusers.microsoft.com/t5/Ideas-for-Human-Resources/idb-p/HumanResources).
    
W przesyłanych opiniach i recenzjach produktu nie podawaj żadnych danych osobowych (tzn. informacji, które mogłyby Cię identyfikować). Zebrane informacje mogą być dalej analizowane, ale ze względu na obowiązujące przepisy o ochronie danych osobowych nie będą wykorzystywane do udzielania odpowiedzi na pytania. Dane osobowe, które na mocy tych programów są zbierane osobno, podlegają [zasadom zachowania poufności informacji firmy Microsoft](https://privacy.microsoft.com/privacystatement).

## <a name="see-also"></a>Informacje dodatkowe

- [Co nowego: Human Resources](hr-admin-whats-new.md)
- [Plan wydawniczy rozwiązań Dynamics 365 i Power Platform](/dynamics365/release-plans/?panel=products1#pivot=products)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
