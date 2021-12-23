---
title: Ustawianie grup podatków dla pozycji
description: W tym temacie wyjaśniono sposób konfigurowania grup podatków dla pozycji w usłudze obliczania podatku.
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
ms.openlocfilehash: 88dd8e2fd9d4d4e5172dcc7b1bd27a70a2f59f03
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2021
ms.locfileid: "7883872"
---
# <a name="set-up-item-tax-groups"></a>Ustawianie grup podatków dla pozycji

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono sposób konfigurowania grup podatków dla pozycji w usłudze obliczania podatku. Wyjaśniono w nim również sposób konfigurowania macierzy reguł stosowania grupy podatków dla pozycji oraz konfigurowania wierszy w macierzy.

Pojęcie grup podatków dla pozycji w usłudze obliczania podatku przypomina pojęcie grup podatków dla pozycji w aplikacji Microsoft Dynamics 365 Finance. Są to grupy kodów podatków. Do określania kodów podatków usługa obliczania podatku używa części wspólnej grupy podatków i grupy podatków dla pozycji.

> [!IMPORTANT]
> Konfiguracja grup podatków dla pozycji w usłudze obliczania podatku jest niezależna od osoby prawnej. Tę konfigurację można wykonać tylko jeden raz w usłudze RCS (Regulatory Configuration Service). Po włączeniu usługi obliczania podatku w aplikacji Finance kody podatków są automatycznie synchronizowane dla wybranej osoby prawnej.

## <a name="set-up-an-item-tax-group"></a>Ustawianie grupy podatków dla pozycji 

Wykonaj następujące kroki, aby skonfigurować grupę podatków dla pozycji:

1. Zaloguj się do usługi [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/).
2. Przejdź kolejno do pozycji **Obszary robocze** \> **Funkcje globalizacji** \> **Obliczanie podatku**.
3. Wybierz funkcję i wersję, które chcesz skonfigurować, a następnie wybierz pozycję **Edytuj**.
4. Na karcie **Ogólne** wybierz pozycję **Wersja konfiguracji**.
5. Na karcie **Grupa podatków dla pozycji** wybierz opcję **Zarządzaj kolumnami**. Jeśli grupa podatków dla pozycji jest konfigurowana po raz pierwszy, pola w oknie dialogowym **Zarządzanie kolumnami** są ustawiane automatycznie.
6. Na liście po lewej stronie rozwiń węzeł **Wiersze** i zaznacz pole wyboru **Grupa podatków dla pozycji**.

    ![Grupa podatków dla pozycji wybrana w węźle Wiersze w oknie dialogowym Zarządzanie kolumnami.](media/select-item-tax-group.png)

7. Wybierz przycisk strzałki w prawo, aby dodać opcję **Grupa podatków dla pozycji** do listy **Wybrane kolumny** z prawej strony.

    ![Opcja Grupa podatków dla pozycji dodana do listy Wybrane kolumny.](media/add-item-tax-group.png)

8. Kliknij przycisk **OK**.

## <a name="configure-an-item-tax-group"></a>Konfigurowanie grupy podatków dla pozycji

Po skonfigurowaniu grupy podatków dla pozycji zostanie utworzona macierz reguł stosowania. W celu skonfigurowania grupy podatków dla pozycji można dodawać wiersze do macierzy.

1. Na karcie **Grupa podatków dla pozycji** wybierz opcję **Dodaj**.
2. W polu **Grupa podatków dla pozycji** nadaj nazwę grupie podatków dla pozycji.

    > [!IMPORTANT]
    > Zalecamy, aby ograniczyć nazwę grupy podatków dla pozycji do 10 znaków. Ta nazwa jest synchronizowana z aplikacją Finance, która ma limit 10 znaków dla nazw grup podatków dla pozycji.

3. W polu **Kody podatków** zaznacz pole wyboru dla każdego kodu podatku, który chcesz uwzględnić w grupie podatków dla pozycji. W jednej grupie podatków dla pozycji można uwzględnić wiele kodów podatków.

    ![Wiele kodów podatków wybranych w polu Kody podatków.](media/multiple-tax-codes-selection.png)

4. Powtórz kroki od 1 do 3, aby dodać więcej grup podatków dla pozycji.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
