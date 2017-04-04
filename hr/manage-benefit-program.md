---
title: "Definiowanie i zarządzanie programu świadczeń"
description: "W module Zasoby ludzkie dostępny jest pakiet narzędzi służących do konfigurowania i obsługi świadczeń, potrąceń i planów wynagrodzeń pracowników, które organizacja oferuje swoim pracownikom lub przetwarza w ich imieniu. Ten artykuł zawiera informacje o sposobie konfigurowania zarządzania świadczeniami."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmBenefitEligibilityDetail, HcmBenefitSelection, SysPolicyListPage, SysPolicySourceDocumentRuleType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 81b5c9056001b26c33b2b42a95711ff5b50243e6
ms.openlocfilehash: 9d00d8f6dfa075f53473af31c257deb57c9efa86
ms.lasthandoff: 03/31/2017


---

# <a name="define-and-manage-a-benefits-program"></a>Definiowanie i zarządzanie programu świadczeń

W module Zasoby ludzkie dostępny jest pakiet narzędzi służących do konfigurowania i obsługi świadczeń, potrąceń i planów wynagrodzeń pracowników, które organizacja oferuje swoim pracownikom lub przetwarza w ich imieniu. Ten temat dostarcza informacji na temat sposobu konfigurowania korzyści Zarządzaj.

<a name="benefit-setup"></a>Konfigurację świadczeń
-------------

Aby przypisać pracownika do świadczenia, trzeba najpierw utworzyć elementy poszczególnych świadczeń. Te elementy łączą podobne plany świadczeń i określają domyślne ustawienia, takie jak stawki potrąceń i szczegóły księgowania. Wiele z tych ustawień można dostosować później, bo przypisywaniu pracowników do świadczeń. Dla każdego planu świadczenia organizacja może oferować kilka opcji rejestrowania lub pracownik może zrezygnować z rejestracji w planie. 

[![Przebieg procesu świadczeń](./media/benefit-process-flow1.png)](./media/benefit-process-flow1.png)

## <a name="benefit-elements"></a>Elementy świadczenia
Przed przystąpieniem do tworzenia świadczeń i przypisywania do nich pracowników, trzeba zdefiniować elementy, które składają się na świadczenie: typ, plan i opcje.

-   **Typ** — zbiór planów szczególnych korzyści, takich jak ochrona zdrowia lub parkowanie.
-   **Plan** — szczególne świadczenie zakontraktowane u dostawcy.
-   **Opcja** — poziom zapotrzebowania, na przykład tylko pracownik lub pracownik i współmałżonek/partner(ka).

Dla każdego typu świadczenia, np. badania okulistyczne lub opieka stomatologiczna, organizacja może oferować pracownikom jeden lub kilka planów. Dla każdego planu organizacja może oferować różne opcje. Na przykład pracownicy mogą wykupić dodatkowy zakres ubezpieczenia o wartości swojego rocznego wynagrodzenia, albo dwu- lub trzykrotnie przewyższającej tę wartość. Każda kombinacja planu i opcji staje się świadczeniem, na jakie pracownicy mogą się zarejestrować. 

[![korzyści pic](./media/benefit-pic.png)](./media/benefit-pic.png)

## <a name="eligibility"></a>Uprawnienie
Dostępność świadczeń oferowanych przez pracodawcę zależy od różnych czynników. Podczas tworzenia świadczenie usługi Microsoft Dynamics 365 dla operacji, można ustawić typ kwalifikacji, które stosuje się do tego świadczenia. 

Korzyści można udostępnić wszystkim pracownikom. Na przykład niektóre firmy oferują przebiegów postojowe wszystkim pracownikom jako progów zysku. Podczas tworzenia tego świadczenia, należy ustawić dostępność na **Dostępne dla wszystkich pracowników**. 

Dla innych korzyści, takich jak garnishments i opłaty podatku nie dotyczy kwalifikowalności. Serwatka tworzyć te typy świadczeń, Kwalifikowalność jest ustawiona na **ominięcie przetwarzania uprawnień do**. 

Wreszcie uprawnienia do świadczenia mogą być oparte na regułach. Na przykład firma oferuje dwa rodzaje świadczenie ubezpieczeń na życie do pracowników. Wykonawczy pracowników kwalifikują się do jednego planu ubezpieczeń na życie, natomiast innych pracowników pełnoetatowych kwalifikują się do innego programu ubezpieczeń na życie. W usłudze Dynamics 365 dla operacji można utworzyć regułę uprawnień do świadczeń, aby znaleźć wszystkich pracowników wykonawczy i innej reguły, aby znaleźć wszystkich pracowników pełnoetatowych i następnie stosują te zasady do odpowiednich świadczeń.

## <a name="enrollment"></a>Rejestracja
Po utworzeniu świadczenia oferowanego w Twojej organizacji i określeniu dostępności, można zarejestrować w nich pracowników. W jednym procesie można zarejestrować jednego pracownika w świadczeniu lub wielu pracowników w jednym lub kilku świadczeniach. 

Czasami organizacja wstrzymuje realizację jakiegoś świadczenia. W takim przypadku należy zaktualizować korzyści i pracowników, którzy są włączeni. Wygaśnięcia świadczeń masy pozwala zmienić datę wygaśnięcia tego świadczenia w tym samym czasie zarówno świadczeń i rejestracje pracownika. Można również wybrać wielu pracowników, którzy są zarejestrowani do świadczenia i zmienić datę końcową ich polisy. 

To samo dotyczy grupowego przedłużania świadczeń, za pomocą którego można wydłużyć datę ważności zarówno dla świadczenia, jak i dla rejestracji pracowników w danym świadczeniu, jeśli świadczenie ma być oferowane dłużej, niż pierwotnie zaplanowano.

<a name="see-also"></a>Informacje dodatkowe
--------

[Benefit eligibility policies](benefit-eligibility-policies.md)


