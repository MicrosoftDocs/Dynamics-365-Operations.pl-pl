---
title: Dodawanie wymiarów finansowych do obszaru roboczego Dyrektor finansowy
description: W tym artykule wyjaśniono, jak dodawać wymiary finansowe do obszaru roboczego Dyrektor finansowy, dzięki czemu będzie można ich używać w raportach ksiąg i budżetów.
author: aprilolson
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: ea453eed826dec2e97371ec559e91b94933bdce6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853388"
---
# <a name="add-financial-dimensions-to-the-cfo-workspace"></a>Dodawanie wymiarów finansowych do obszaru roboczego Dyrektor finansowy

[!include [banner](../includes/banner.md)]

W tym artykule wyjaśniono, jak dodawać wymiary finansowe do obszaru roboczego Dyrektor finansowy, dzięki czemu będzie można ich używać w raportach ksiąg i budżetów. Obszar roboczy Dyrektor finansowy zawiera kartę **Przegląd** i kartę **Finanse**. Raporty na tych dwóch kartach dodatkowo wykorzystują dwie miary: LedgerActivityMeasure i BudgetActivityMeasure. Występuje zbiór między tymi dwoma miarami i jednostką DimensionCombinationEntity. W związku z tym można wybierać wymiary.

1. W aplikacji Finance na stronie **Magazyn jednostek** zaktualizuj miary **LedgerActivityMeasure** i **BudgetActivityMeasure**.
2. W programie Microsoft Visual Studio otwórz Eksploratora aplikacji i wyszukaj element **LedgerCFO**.
3. W obszarze **Zasoby** otwórz zasób **LedgerCFOWorkspacePBIX**.
4. Gdy zasób zostanie otwarty na pulpicie Microsoft Power BI, wybierz kolejno opcje **Pobierz dane**, **Baza danych programu SQL Server** i **Połącz**.
5. Wprowadź nazwę serwera, a jako bazę danych wpisz **AxDW**. Zaznacz element **DirectQuery** i kliknij przycisk **OK**.
6. Wyszukaj i zaznacz element **LedgerActivityMeasure\_DimensionCombination**, a następnie wybierz opcję **Załaduj**.

    > [!TIP]
    > Na liście **Pola** zmień nazwę tabeli na **Wymiary finansowe**, tak aby łatwiej ją było zidentyfikować.

7. Wybierz kolejno opcje **Zarządzanie relacjami** i **Nowy**.
8. W pierwszym polu wybierz opcję **Działania na księdze głównej**, a następnie zaznacz element **LedgerDimension**.
9. W drugim polu zaznacz element **LedgerActivityMeasure\_DimensionCombination** (lub **Wymiary finansowe**, jeśli nazwa tabeli została zmieniona). Zaznacz nagłówek **DimensionCombinationRECID**.
10. W polu **Kardynalność** zaznacz opcję **Wiele do jednego**.
11. W polu **Kierunek filtrowania krzyżowego** zmień wartość na **Pojedyncze**.
12. Zaznacz opcje **Aktywuj tę relację** i **Przyjmij integralność referencyjną**, a następnie kliknij kolejno przyciski **OK** i **Anuluj**.

    [![Tworzenie relacji.](./media/Create-relationship.png)](./media/Create-relationship.png)

13. Na liście **Pola** powinna być widoczna tabela oraz dostępne wymiary finansowe. Przeciągnij żądane wymiary finansowe do filtrów na poziomie raportu.
14. Zapisz zmiany.
15. W drzewie obiektów aplikacji (AOT) kliknij prawym przyciskiem myszy swój projekt i wybierz polecenie **Synchronizuj**.
16. Skompiluj projekt, a następnie otwórz aplikację, aby wyświetlić rezultat.

    [![Skonfigurowana przestrzeń robocza.](./media/workspace.png)](./media/workspace.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
