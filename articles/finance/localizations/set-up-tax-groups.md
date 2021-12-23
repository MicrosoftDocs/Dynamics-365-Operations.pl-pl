---
title: Konfigurowanie grup podatków
description: W tym temacie wyjaśniono sposób konfigurowania grup podatków w usłudze obliczania podatku.
author: wangchen
ms.date: 11/30/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-10-26
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 50abafb958edfb8476434ff5842cd84cb186962f
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2021
ms.locfileid: "7883874"
---
# <a name="set-up-tax-groups"></a>Konfigurowanie grup podatków

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono sposób konfigurowania grup podatków w usłudze obliczania podatku. Wyjaśniono w nim również sposób konfigurowania macierzy reguł stosowania grupy podatków oraz konfigurowania wierszy w macierzy.

Pojęcie grup podatków w usłudze obliczania podatku przypomina pojęcie grup podatków w aplikacji Microsoft Dynamics 365 Finance. Są to grupy kodów podatków. Do określania kodów podatków usługa obliczania podatku używa części wspólnej grupy podatków i grupy podatków dla pozycji.

Jednak grupy podatków w usłudze obliczania podatku różnią się od grup podatków w aplikacji Finance, ponieważ nie istnieją w nich dodatkowe parametry, takie jak **Ewentualny podatek obrotowy** czy **Zwolnienie z podatku**. Zamiast tego te parametry są dostępne na poziomie kodu podatku.

> [!IMPORTANT]
> Konfiguracja grup podatków w usłudze obliczania podatku jest niezależna od osoby prawnej. Tę konfigurację można wykonać tylko jeden raz w usłudze RCS (Regulatory Configuration Service). Po włączeniu usługi obliczania podatku w aplikacji Finance kody podatków są automatycznie synchronizowane dla wybranej osoby prawnej.

## <a name="set-up-a-tax-group"></a>Ustawianie grupy podatków

Wykonaj poniższe kroki, aby skonfigurować grupę podatków.

1. Zaloguj się do usługi [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/).
2. Przejdź kolejno do pozycji **Obszary robocze** \> **Funkcje globalizacji** \> **Obliczanie podatku**.
3. Wybierz funkcję i wersję, które chcesz skonfigurować, a następnie wybierz pozycję **Edytuj**.
4. Na karcie **Ogólne** wybierz pozycję **Wersja konfiguracji**.
5. Na karcie **Grupa podatków** wybierz opcję **Zarządzaj kolumnami**. Jeśli grupa podatków jest konfigurowana po raz pierwszy, pola w oknie dialogowym **Zarządzanie kolumnami** są ustawiane automatycznie.
6. Na liście po lewej stronie rozwiń węzeł **Wiersze** i zaznacz pole wyboru **Grupa podatków**.

    ![Grupa podatków wybrana w węźle Wiersze w oknie dialogowym Zarządzanie kolumnami.](media/select-tax-group.png)

7. Wybierz przycisk strzałki w prawo, aby dodać opcję **Grupa podatków** do listy **Wybrane kolumny** z prawej strony.

    ![Opcja Grupa podatków dodana do listy Wybrane kolumny.](media/add-tax-group.png)

8. Kliknij przycisk **OK**.

## <a name="configure-a-tax-group"></a>Konfigurowanie grupy podatków

Po skonfigurowaniu grupy podatków zostanie utworzona macierz reguł stosowania grupy podatków. W celu skonfigurowania grupy podatków można dodawać wiersze do macierzy.

1. Na karcie **Grupa podatków** wybierz przycisk **Dodaj**.
2. W polu **Grupa podatków** nadaj nazwę grupie podatków.

    > [!IMPORTANT]
    > Zalecamy, aby ograniczyć nazwę grupy podatków do 10 znaków. Ta nazwa jest synchronizowana z aplikacją Finance, która ma limit 10 znaków dla nazw grup podatków.

3. W polu **Kody podatków** zaznacz pole wyboru dla każdego kodu podatku, który chcesz uwzględnić w grupie podatków. W jednej grupie podatków można uwzględnić wiele kodów podatków.

    ![Wiele kodów podatków wybranych w polu Kody podatków.](media/multiple-tax-codes-selection.png)

4. Powtórz kroki od 1 do 3, aby dodać więcej grup podatków.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
