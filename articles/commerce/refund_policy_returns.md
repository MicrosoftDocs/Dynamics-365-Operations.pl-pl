---
title: Tworzenie i aktualizowanie zasad zwrotów i refundacji dla kanału
description: W tym artykule wyjaśniono, jak skonfigurować zasady zwrotu i zwrotów dla kanału.
author: ShalabhjainMSFT
ms.date: 07/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2020-01-21
ms.dyn365.ops.version: Retail 10.0.9 update
ms.openlocfilehash: 54dd19134aea68f73de51086fbaa096961447b62
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873311"
---
# <a name="create-and-update-a-returns-and-refunds-policy-for-a-channel"></a>Tworzenie i aktualizowanie zasad zwrotów i refundacji dla kanału

[!include [banner](includes/banner.md)]

Zasady dotyczące zwrotów kanałów w systemie Dynamics 365 Commerce umożliwiają detalistom Konfigurowanie wymuszeń, dla których może być dozwolone przetworzenie zwrotów na urządzeniu punktu sprzedaży (POS).  

W tym artykule wyjaśniono kroki, jak skonfigurować zasady zwrotu i zwrotów dla kanału.

Zakres zasad obecnie ogranicza się do ustawiania ofert płatności, które mogą być dozwolone dla kanału. Lista „dozwolone” jest oparta na metodach płatności używanych do dokonywania zakupu. Na przykład:

- Jeśli zakup został dokonany przy użyciu karty upominkowej, zasady sklepu umożliwiają przetwarzanie zwrotów tylko na nową kartę upominkową lub na kredyt sklepowy. 
- Jeśli sprzedaż zostanie dokonana przy użyciu środków pieniężnych, opcje dozwolone dla zwrotu to gotówka, karta upominkowa i konto odbiorcy, ale nie karta kredytowa. 

## <a name="enable-return-policy"></a>Włącz zasady zwrotów

Aby włączyć funkcję zasad zwrotów kanału w centrali handlowej, wykonaj następujące kroki.

1. Otwórz obszar roboczy **Zarządzanie funkcjami** w Dynamics 365 Commerce.
1. Wyszukaj funkcję **Włącz zasady zwrotów kanału** na liście nazw funkcji.
1. Wybierz **Włącz teraz**.
1. Na stronie **Harmonogram dystrybucji** uruchom zadanie **1110** (Konfiguracja globalna) w celu dystrybucji zmiany funkcji.

## <a name="configure-return-policy"></a>Konfiguruj zasady zwrotów

Aby skonfigurować zasady dotyczące zwrotów dla sklepu detalicznego lub kanału sprzedaży online, należy wykonać następujące czynności.

1. Przejdź do ustawień **Handel detaliczny i inny** \> **Konfiguracja kanału** \> **Zwroty** \> **Zasady zwrotów kanału**.

1. Naciśnij przycisk **Nowy**, aby utworzyć nowy szablon zasad zwrotów. Aby skorzystać z istniejącego szablonu, wybierz szablon w lewym okienku. W przypadku nowych szablonów należy dodać nazwę i opis, które ułatwią identyfikowanie zasady, kiedy jest ona stosowana w kanale.

   ![Dodaj nowe zasady dotyczące zwrotów.](media/Return-policy-page1.png)
     
   
1. W sekcji **dozwolona Metoda płatności dla zwrotu** Określ **dozwolone** płatności zwrotne, które są właściwe dla każdej metody płatności.
   ![Umożliwia ustawienie dozwolonych metod płatności dla typu płatności.](media/Return-policy-page2.png)
   
    > [!IMPORTANT]
    > - Metody płatności pochodzą z metod płatności ustawionych dla organizacji.
    > - Dodanie dozwolonego typu metody płatności zwrotnej dla każdej wymienionej metody płatności zapewni, że można wprowadzać zwroty do dozwolonego typu metody płatności zwrotnej.
    
1. Szablonem zasad zwrotów należy skojarzyć ze sklepami, w których będzie używany. Wybierz opcję **Dodaj** na karcie **kanały sprzedaży detalicznej** i skojarz dostępne kanały. 

    - W oknie dialogowym **Wybieranie węzłów organizacji** wybierz sklepy, regiony i organizacje, z którymi szablon ma być skojarzony.
    - Z każdym sklepem można skojarzyć tylko jeden szablon zasad zwrotów.
    - Za pomocą przycisków strzałek wybierz sklepy, regiony lub organizacje
    - Data wejścia w życie zasady będzie datą zastosowania zasad do kanałów i uruchomienia zadań kanału. 

    ![Wybierz okienko dialogowe węzły organizacji.](media/Return-policy-page3.png)

1. Na stronie **harmonogram dystrybucji** Uruchom zadanie **1070**, aby zasady dotyczące zwrotów kanałów były dostępne dla punktu sprzedaży.

## <a name="preview-the-channel-return-policy-in-the-pos"></a>Podgląd zasad dotyczących zwrotów dotyczących kanału w punkcie sprzedaży

Aby wyświetlić dozwolone typy płatności zwrotnych w punkcie sprzedaży, należy wykonać kroki podane w poniższych przykładach.

1. Zaloguj się do punktu sprzedaży jako kasjer lub menedżer.
1. W obszarze **Zmiana i szuflada** wybierz opcję **Wyświetl arkusz**.
1. Umożliwia wybranie transakcji, która jest częścią zwrotu. 
1. Wybierz towary do zwrotu i wybierz metodę płatności.  
    - Jeśli wybrana oferta płatności znajduje się na liście dozwolonych typów płatności zwrotnej, kasjer może dokończyć transakcję.
    - Jeśli wybrana oferta płatności jest niedozwolona, zostanie wyświetlony komunikat o błędzie.
    - Wybranie opcji **kwota należna** powoduje wyświetlenie listy wszystkich dozwolonych typów zwrotów płatności.

— lub —

1. Zaloguj się do punktu sprzedaży jako kasjer lub menedżer.
1. Wybierz opcję **transakcja zwrotu** i wprowadź identyfikator paragonu przy użyciu skanowania kodu kreskowego lub za pomocą wpisu ręcznego. 
1. Umożliwia wybranie transakcji, która jest częścią zwrotu. 
1. Wybierz towary do zwrotu i wybierz metodę płatności.  
    - Jeśli wybrana oferta płatności znajduje się na liście dozwolonych typów płatności zwrotnej, kasjer może dokończyć transakcję.
    - Jeśli wybrana oferta płatności jest niedozwolona, zostanie wyświetlony komunikat o błędzie.
    - Wybranie opcji **kwota należna** powoduje wyświetlenie listy wszystkich dozwolonych typów zwrotów płatności.

![Typ płatności zwrotu jest niedozwolony.](media/Return-policy-page6.png)



![Dozwolone typy płatności zwrotu.](media/Return-policy-page5.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
