---
title: Zaktualizuj numery certyfikatów i daty transakcji TDS
description: W tym temacie wyjaśniono, jak zaktualizować możliwe do odzyskania numery certyfikatów i daty, które zostały zarejestrowane dla kont dostawców, odbiorców i księgowych dla odliczenia podatku u źródła (TDS).
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
ms.openlocfilehash: 248de8e12703a84482b67d0899857a6efb33531c
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023504"
---
# <a name="update-certificate-numbers-and-dates-for-tds-transactions"></a>Zaktualizuj numery certyfikatów i daty transakcji TDS

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak zaktualizować możliwe do odzyskania numery certyfikatów i daty, które zostały zarejestrowane dla kont dostawców, odbiorców i księgowych dla odliczenia podatku u źródła (TDS). Certyfikaty dla transakcji TDS można wyświetlić na stronie **Certyfikaty, które można odzyskać**. Certyfikaty można aktualizować, korzystając ze strony **Aktualizacja certyfikatów**.

Wykonaj poniższe czynności, aby zaktualizować numery certyfikatów i daty transakcji TDS.

1. Przejdź do **Podatek \> Deklaracje \> Zaliczka na podatek \> Płatność zaliczki na podatek**.

    [![Aktualizuj stronę certyfikatu](./media/apac-ind-TDS-45.png)](./media/apac-ind-TDS-45.png)

2. Na stronie **Aktualizuj certyfikat**, w sekcji **Wybierz** w polu **Typ podatku** wybierz pozycję **TDS**.
3. W polu **Numer certyfikatu** wybierz numer certyfikatu TDS odbiorcy lub dostawcy.

    > [!NOTE]
    > W polu **Numer certyfikatu** są dostępne tylko numery certyfikatów TDS, dla których wyczyszcznięto pole wyboru **Zamknięte** na stronie **Certyfikaty możliwe do zwrotu**.

    W polu **Data certyfikatu** pokazana jest data certyfikatu. Pole **Typ konta** zawiera typ konta, dla których otrzymano numer certyfikatu TDS, a pole **Nazwa** zawiera nazwę konta.

5. W polach **Od dnia** i **Do dnia** wybierz datę początkową i końcową okresu, dla którego mają być wyświetlane transakcje potrącenia podatku u źródła.
6. Wybierz pozycję **Pokaż dane**, aby wyświetlić transakcje TDS, które zostały zaksięgowane w wybranym okresie.

    Na karcie **Przegląd** w górnym okienku w siatce są widać następujące informacje o każdej transakcji TDS zaksięgowanej dla dostawcy lub odbiorcy w wybranym okresie:

    - **Załącznik** – Umożliwia wyświetlenie numeru załącznika TDS.
    - **Data** – Data transakcji TDS.
    - **Kwota** – Kwota faktury, na podstawie której obliczono TDS.
    - **Kwota podatku** — kwota podatku TDS obliczona dla transakcji.

7. Aby przenieść określone transakcje TDS z górnej do dolnej siatki, wybierz transakcje, a następnie wybierz opcję **Uwzględnij**. Możesz również wybrać opcję **Uwzględnij wszystko**, aby przenieść wszystkie transakcje TDS z górnej siatki do dolnej siatki.

    Aby przenieść określone transakcje TDS lub wszystkie transakcje TDS z dolnej siatki do górnej siatki, użyj przycisku **Wyklucz** lub **Wyklucz wszystko**.

8. Wybierz przycisk **Aktualizuj**, aby zaktualizować pola **Numer certyfikatu** i **Data certyfikatu** dla transakcji TDS w dolnej siatce.
10. Przejdź do **Podatki \> Indirect taxes \> Potrącona zaliczka na podatek \> Certyfikaty podlegające zwrotowi** i wybierz pozycję **Informacje**, aby wyświetlić zaktualizowane wiersze transakcji, które mają nowe numery certyfikatów na stronie **Transakcje certyfikatu**.

    [![Strona transakcji certyfikatów](./media/apac-ind-TDS-46.png)](./media/apac-ind-TDS-46.png)
