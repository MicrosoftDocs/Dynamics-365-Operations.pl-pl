---
title: Rejestrowanie numerów certyfikatów koncesji TDS
description: W tym temacie wyjaśniono, jak rejestrować numery certyfikatów koncesyjnych wydane dostawcom odliczonego podatku w źródle (TDS).
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
ms.openlocfilehash: 97fce25ea8c556f001c84f6836a0a270a9f3524f
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6358393"
---
# <a name="record-tds-concession-certificate-numbers"></a>Rejestrowanie numerów certyfikatów koncesji TDS

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak rejestrować numery certyfikatów koncesyjnych wydane dostawcom odliczonego podatku w źródle (TDS).

1. Wybierz kolejno opcje **Podatek \> Podatki pośrednie \> Potrącona zaliczka na podatek \> Zwolnienia z podatku u źródła**.
2. W polu **Typ podatku** wybierz identyfikator **TDS**, aby zarejestrować certyfikaty koncesji dla typu podatku TDS.
3. Na karcie **Omówienie** wybierz klawisze **Alt+N**, aby utworzyć wiersz.

    [![Nagłówek nowego wiersza.](./media/apac-ind-TDS-34.png)](./media/apac-ind-TDS-34.png)

4. W polu **Kod potrąconej zaliczki** na podatek wybierz kod podatku TDS, dla których są wystawiane certyfikaty koncesji dostawcy. W polu **Nazwa kodu potrąconej zaliczki na podatek** zawiera nazwę kodu podatku TDS.
5. W polach **Od dnia** i **Do dnia** określ okres ważności dla certyfikatu koncesji, który używa kodu podatku TDS do obliczenia TDS dla dostawcy na podstawie koncesji.
6. W polu **Uwagi** wprowadź uwagi.
7. W polu **Sekcja** wprowadź kod sekcji prawnej, z poziomu których jest dostępny certyfikat koncesji TDS.

    Jeśli kod sekcji ma wartość 197, wartość „A” pojawia się w kolumnie „Przyczyna potrącenia/dolnego potrącenia” w formularzu 26Q oraz w kolumnie „Przyczyna nieuejmowania/dolnego potrącenia/zsumowania (jeśli istnieje)” w formularzu 27Q. Jeśli kod sekcji to 197A, w obu tych miejscach jest wyświetlana wartość „B”.

8. Wybierz skróconą kartę **Certyfikat**, aby rejestrować numery certyfikatów koncesji TDS dla dostawców.
9. W polu **Konto dostawcy** wybierz konto dostawcy, dla których jest wystawiany certyfikat koncesji TDS.
10. W polach **Od dnia** i **Do dnia** określ okres ważności certyfikatu koncesji TDS.

    Podstawą obliczania TDS jako koncesji jest okres, w którym jest tworzony certyfikat dla dostawcy.

11. W polu **Certyfikat** wprowadź numer certyfikatu koncesji TDS.

    [![Skrócona karta certyfikatu.](./media/apac-ind-TDS-33.png)](./media/apac-ind-TDS-33.png)

12. Zamknij stronę.
