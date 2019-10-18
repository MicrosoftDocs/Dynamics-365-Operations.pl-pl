---
title: Tworzenie i przypisywanie struktur reguł zaawansowanych
description: W tym temacie wyjaśniono, jak utworzyć i przypisać strukturę reguły zaawansowanej do struktury konta.
author: aprilolson
manager: AnnBe
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountRuleStructure, DimensionCreateAccountRuleStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate, DimensionConfigureAccountStructure, DimensionConfigureAccountRule, DimensionCreateAccountRule, DimensionSelectAccountRuleStructure
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cff07c13553ea140f537160da7f93820d5e3f77a
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2175587"
---
# <a name="create-and-assign-advanced-rule-structures"></a>Tworzenie i przypisywanie struktur reguł zaawansowanych

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tym temacie wyjaśniono, jak utworzyć i przypisać strukturę reguły zaawansowanej do struktury konta. W przewodniku jest wykorzystywana firma demonstracyjna USMF.

## <a name="create-an-advanced-rule-structure"></a>Utwórz strukturę reguły zaawansowanej
1. Wybierz kolejno opcje **Okienko nawigacji > Moduły > Księga główna > Plan kont > Struktury > Struktury reguł zaawansowanych**.
2. Wybierz **Nowe**, aby otworzyć listę rozwijania.
3. W polu **Struktura reguły zaawansowanej** wprowadź nazwę opisującą strukturę reguły.
4. Kliknij przycisk **OK**.
5. Wybierz opcję **Dodaj segment**.
6. Na liście segmentów wybierz wymiar finansowy. Na przykład **Sklep**.  
7. Wybierz opcję **Dodaj segment**.
8. Wybierz **Aktywuj**.

## <a name="apply-an-advanced-rule-structure-to-an-account-structure"></a>Stosowanie struktury reguły zaawansowanej do struktury konta
1. Wybierz kolejno opcje **Okienko nawigacji > Moduły > Księga główna > Plan kont > Struktury > Konfigurowanie struktur kont**.
2. Na liście znajdź i wybierz strukturę konta, do której chcesz zastosować regułę zaawansowaną.
3. Wybierz opcję **Edycja**. Można także wybrać opcję **Reguły zaawansowane**, a pojawi się monit o przełączenie struktury konta do **Trybu roboczego**.  
4. Wybierz opcję **Reguły zaawansowane**.
5. Wybierz **Nowe**, aby otworzyć listę rozwijania.
6. W polu **Reguła zaawansowana** wpisz wartość.
7. W polu **Nazwa** wpisz wartość.
8. Wybierz opcję **Utwórz**.
9. Wybierz opcję **Dodaj nowe kryteria**.
10. W polu **Gdzie** wybierz konto główne lub wymiar finansowy.
11. W polu **Operator** wybierz opcję, taką jak **zawiera się między** lub **zawiera**.
12. W polu **Wartość** wpisz wartość.
13. W polu **za pomocą** wpisz wartość.
14. Wybierz przycisk **Dodaj**, aby otworzyć rozwijane okno dialogowe.
15. Na liście znajdź strukturę reguły zaawansowanej, która ma być używana po spełnieniu wprowadzonych kryteriów.
16. Wybierz opcję **Dodaj**.
17. Zamknij stronę.
18. Wybierz **Aktywuj**.

