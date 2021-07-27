---
title: Konfigurowanie parametrów podatku TDS w modułach Rozrachunki z dostawcami i Rozrachunki z odbiorcami
description: W tym temacie wyjaśniono, jak ustawić parametry w rozrachunkach z dostawcami i rozrachunkach z odbiorcami w celu obsługi potrąceń podatku u źródła (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: ccf1557d3c95829421b26d5f84750e3d4236c9e0
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6358225"
---
# <a name="set-tds-parameters-in-accounts-payable-and-accounts-receivable"></a>Konfigurowanie parametrów podatku TDS w modułach Rozrachunki z dostawcami i Rozrachunki z odbiorcami

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak ustawić parametry w rozrachunkach z dostawcami i rozrachunkach z odbiorcami w celu obsługi potrąceń podatku u źródła (TDS).

1. Wybierz kolejno pozycje **Tax \> Ustawienia \> Parametry \> Parametry modułu rozrachunków z odbiorcami**.
2. Na karcie **Aktualizacje** wybierz opcję **Aktualizuj wiersze zamówienia**, aby otworzyć okno dialogowe **Aktualizacja wierszy zamówienia**.
3. W sekcji **Grupa TDS**, w polu **Aktualizacja grupy TDS** określ metodę aktualizacji grupy TDS na poziomie wiersza. To ustawienie jest używane podczas aktualizowania grupy TDS w nagłówku zamówienia. Dostępne są następujące opcje:

    - **Nigdy** — grupa TDS nie jest aktualizowana w wierszach zamówienia, gdy jest aktualizowana w nagłówku zamówienia.
    - **Zawsze** — Grupa TDS jest automatycznie aktualizowana w wierszach zamówienia, gdy jest aktualizowana w nagłówku zamówienia.
    - **Monituj** — użytkownicy otrzymują komunikat z monitem o aktualizację grupy TDS w wierszach zamówienia.
4. Kliknij przycisk **OK**.

    [![Okno dialogowe aktualizacji wierszy zamówienia.](./media/apac-ind-TDS-26.PNG)](./media/apac-ind-TDS-26.PNG)

5. Wybierz kolejno pozycje **Tax \> Ustawienia \> Parametry \> Parametry modułu rozrachunków z dostawcami**.
6. Na karcie **Ogólne**, na skróconej karcie **Podziel na podstawie informacji o dostawie** dla opcji **Dokumentu przyjęcia produktów** ustaw wartość **Tak** daby zakwitować i podzielić przyjęcie produktów, które ma różne adresy dostawy i numery kont podatkowych (TAN). Jeśli ta opcja ma wartość **Nie**, nie można zakłać dokumentu dostawy zakupu, który ma różne adresy dostawy i ten typ.
7. Ustaw dla **faktury** wartość **Tak**, aby zakturować i podzielić fakturę zakupu, która ma różne adresy dostawy i numer TAN.

    [![Podział na podstawie informacji o dostawie Skrócona karta.](./media/apac-ind-TDS-25.png)](./media/apac-ind-TDS-25.png)

8. Zamknij stronę.
