---
title: Definiowanie programu świadczeń i zarządzanie nim
description: W module Zasoby ludzkie dostępny jest pakiet narzędzi służących do konfigurowania i obsługi świadczeń, potrąceń i planów wynagrodzeń pracowników, które organizacja oferuje swoim pracownikom lub przetwarza w ich imieniu. Ten artykuł zawiera informacje o sposobie konfigurowania zarządzania świadczeniami.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, HcmBenefitSelection, SysPolicyListPage, SysPolicySourceDocumentRuleType, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 1616f4ac72668e8dd0b9ff3d6962848871b1bbc6
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5804992"
---
# <a name="define-and-manage-a-benefits-program"></a>Definiowanie programu świadczeń i zarządzanie nim

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W module Human Resources dostępny jest pakiet narzędzi służących do konfigurowania i obsługi świadczeń, potrąceń i planów wynagrodzeń pracowników, które organizacja oferuje swoim pracownikom lub przetwarza w ich imieniu. Ten artykuł zawiera informacje o sposobie konfigurowania świadczeń i zarządzania nimi.

## <a name="benefit-setup"></a>Konfiguracja świadczeń

Aby przypisać pracownika do świadczenia, trzeba najpierw utworzyć elementy poszczególnych świadczeń. Te elementy łączą podobne plany świadczeń i określają domyślne ustawienia, takie jak stawki potrąceń i szczegóły księgowania. Wiele z tych ustawień można dostosować później, bo przypisywaniu pracowników do świadczeń. Dla każdego planu świadczenia organizacja może oferować kilka opcji rejestrowania lub pracownik może zrezygnować z rejestracji w planie. 

[![Przebieg procesu świadczeń](./media/benefit-process-flow1.png)](./media/benefit-process-flow1.png)

## <a name="benefit-elements"></a>Elementy świadczenia

Przed przystąpieniem do tworzenia świadczeń i przypisywania do nich pracowników, trzeba zdefiniować elementy, które składają się na świadczenie: typ, plan i opcje.

-   **Typ** — zbiór planów szczególnych korzyści, takich jak ochrona zdrowia lub parkowanie.
-   **Plan** — szczególne świadczenie zakontraktowane u dostawcy.
-   **Opcja** — poziom zapotrzebowania, na przykład tylko pracownik lub pracownik i współmałżonek/partner(ka).

Dla każdego typu świadczenia, np. badania okulistyczne lub opieka stomatologiczna, organizacja może oferować pracownikom jeden lub kilka planów. Dla każdego planu organizacja może oferować różne opcje. Na przykład pracownicy mogą wykupić dodatkowy zakres ubezpieczenia o wartości swojego rocznego wynagrodzenia, albo dwu- lub trzykrotnie przewyższającej tę wartość. Każda kombinacja planu i opcji staje się świadczeniem, na jakie pracownicy mogą się zarejestrować. 

[![ilustracja świadczenia](./media/benefit-pic.png)](./media/benefit-pic.png)

## <a name="eligibility"></a>Uprawnienie
Dostępność świadczeń oferowanych przez pracodawcę zależy od różnych czynników. Podczas tworzenia świadczenia w programie Dynamics 365 Human Resources można ustawić dla niego typ uprawnień. 

Można udostępnić świadczenie wszystkim pracownikom. Na przykład niektóre firmy oferują przepustki parkingowe wszystkim pracowniom jako świadczenia nieodpłatne. Podczas tworzenia tego świadczenia, należy ustawić dostępność na **Dostępne dla wszystkich pracowników**. 

W przypadku innych świadczeń, takich jak zajęcia wierzytelności lub opłaty podatkowe, opcje uprawnień nie mają zastosowania. Podczas tworzenia świadczeń tego typu ustawia się uprawnienia na **Pomiń przetwarzanie uprawnień**. 

Uprawnienia do świadczeń mogą również opierać się na regułach. Na przykład firma oferuje pracownikom dwa rodzaje ubezpieczeń na życie. Członkowie kadry kierowniczej są uprawnieni do jednego planu ubezpieczenia na życie, a dla pozostałych pracowników pełnoetatowych dostępny jest inny plan ubezpieczenia na życie. W module Human Resources można utworzyć regułę wyszukującą wszystkich członków kadry kierowniczej oraz regułę wyszukującą wszystkich pozostałych pracowników pełnoetatowych, a następnie zastosować te reguły do odpowiedniego świadczenia.

## <a name="enrollment"></a>Rejestracja
Po utworzeniu świadczenia oferowanego w Twojej organizacji i określeniu dostępności, można zarejestrować w nich pracowników. W jednym procesie można zarejestrować jednego pracownika w świadczeniu lub wielu pracowników w jednym lub kilku świadczeniach. 

Czasami organizacja wstrzymuje realizację jakiegoś świadczenia. W takim przypadku trzeba zaktualizować świadczenie i zarejestrowanych w nim pracowników. Grupowe wygaszanie świadczenia pozwala za jednym razem zmienić datę ważności zarówno dla świadczenia, jak i dla rejestracji pracowników w tym świadczeniu. Można również wybrać wielu pracowników, którzy są zarejestrowani do świadczenia i zmienić datę końcową ich polisy. 

To samo dotyczy grupowego przedłużania świadczeń, za pomocą którego można wydłużyć datę ważności zarówno dla świadczenia, jak i dla rejestracji pracowników w danym świadczeniu, jeśli świadczenie ma być oferowane dłużej, niż pierwotnie zaplanowano.




[!INCLUDE[footer-include](../includes/footer-banner.md)]