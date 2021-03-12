---
title: Tworzenie i aktualizowanie zasad zwrotu i zwrotów dla kanału
description: W tym temacie wyjaśniono, jak skonfigurować zasady zwrotu i zwrotów dla kanału.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2020-01-21
ms.dyn365.ops.version: Retail 10.0.9 update
ms.openlocfilehash: 89e8fe78414e73053317ebe19e3afcc89231d440
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979727"
---
# <a name="create-and-update-a-returns-and-refunds-policy-for-a-channel"></a>Tworzenie i aktualizowanie zasad zwrotu i zwrotów dla kanału

[!include [banner](includes/banner.md)]

## <a name="overview"></a>Omówienie

Zasady dotyczące zwrotów kanałów w systemie Dynamics 365 Commerce umożliwiają detalistom Konfigurowanie wymuszeń, dla których może być dozwolone przetworzenie zwrotów na urządzeniu punktu sprzedaży (POS).  

W tym temacie wyjaśniono kroki, jak skonfigurować zasady zwrotu i zwrotów dla kanału.

Zakres zasad obecnie ogranicza się do ustawiania ofert płatności, które mogą być dozwolone dla kanału. Lista „dozwolone” jest oparta na metodach płatności używanych do dokonywania zakupu. Na przykład:

- Jeśli zakup został dokonany przy użyciu karty upominkowej, zasady sklepu umożliwiają przetwarzanie zwrotów tylko na nową kartę upominkową lub na kredyt sklepowy. 
- Jeśli sprzedaż zostanie dokonana przy użyciu środków pieniężnych, opcje dozwolone dla zwrotu to gotówka, karta upominkowa i konto odbiorcy, ale nie karta kredytowa. 


## <a name="enable-return-policy"></a>Włącz zasady zwrotów

Aby włączyć funkcję zasad dotyczących zwrotów kanałów, wykonaj następujące czynności:

1. Otwórz obszar roboczy **Zarządzanie funkcjami** w Dynamics 365 Commerce.
2. Wyszukaj funkcję **Włącz zasady zwrotów kanału** na liście nazw funkcji.
3. Wybierz **Włącz teraz**. 

## <a name="configure-return-policy"></a>Konfiguruj zasady zwrotów

Aby skonfigurować zasady dotyczące zwrotów dla sklepu detalicznego lub kanału sprzedaży online, należy wykonać następujące czynności.

1. Przejdź do ustawień **Handel detaliczny i inny** \> **Konfiguracja kanału** \> **Zwroty** \> **Zasady zwrotów kanału**.

2. Naciśnij przycisk **Nowy**, aby utworzyć nowy szablon zasad zwrotów. Aby skorzystać z istniejącego szablonu, wybierz szablon w lewym okienku. W przypadku nowych szablonów należy dodać nazwę i opis, które ułatwią identyfikowanie zasady, kiedy jest ona stosowana w kanale.

   ![Dodaj nowe zasady dotyczące zwrotów](media/Return-policy-page1.png "Dodaj nowe zasady dotyczące zwrotów")
     
   
3. W sekcji **dozwolona Metoda płatności dla zwrotu** Określ **dozwolone** płatności zwrotne, które są właściwe dla każdej metody płatności.
   ![Dodaj metody płatności](media/Return-policy-page2.PNG "Umożliwia ustawienie dozwolonych metod płatności dla typu płatności")
   
    > [!IMPORTANT]
    > - Metody płatności pochodzą z metod płatności ustawionych dla organizacji.
    > - Dodanie dozwolonego typu metody płatności zwrotnej dla każdej wymienionej metody płatności zapewni, że można wprowadzać zwroty do dozwolonego typu metody płatności zwrotnej.
    
4. Szablonem zasad zwrotów należy skojarzyć ze sklepami, w których będzie używany. Wybierz opcję **Dodaj** na karcie **kanały sprzedaży detalicznej** i skojarz dostępne kanały. 

    - W oknie dialogowym **Wybieranie węzłów organizacji** wybierz sklepy, regiony i organizacje, z którymi szablon ma być skojarzony.
    - Z każdym sklepem można skojarzyć tylko jeden szablon zasad zwrotów.
    - Za pomocą przycisków strzałek wybierz sklepy, regiony lub organizacje
    - Data wejścia w życie zasady będzie datą zastosowania zasad do kanałów i uruchomienia zadań kanału. 

    ![Wybierz okienko dialogowe węzły organizacji](media/Return-policy-page3.PNG "Wybierz okienko dialogowe węzły organizacji")

5. Na stronie **harmonogram dystrybucji** Uruchom zadanie **1070**, aby zasady dotyczące zwrotów kanałów były dostępne dla punktu sprzedaży.

## <a name="preview-the-channel-return-policy-in-the-pos"></a>Podgląd zasad dotyczących zwrotów dotyczących kanału w punkcie sprzedaży

Aby wyświetlić dozwolone typy płatności zwrotnych w punkcie sprzedaży, należy wykonać kroki podane w poniższych przykładach.

1. Zaloguj się do punktu sprzedaży jako kasjer lub menedżer.
2. W obszarze **Zmiana i szuflada** wybierz opcję **Wyświetl arkusz**.
3. Umożliwia wybranie transakcji, która jest częścią zwrotu. 
4. Wybierz towary do zwrotu i wybierz metodę płatności.  
- Jeśli wybrana oferta płatności znajduje się na liście dozwolonych typów płatności zwrotnej, kasjer może dokończyć transakcję.
- Jeśli wybrana oferta płatności jest niedozwolona, zostanie wyświetlony komunikat o błędzie.
- Wybranie opcji **kwota należna** powoduje wyświetlenie listy wszystkich dozwolonych typów zwrotów płatności.

— lub —

1. Zaloguj się do punktu sprzedaży jako kasjer lub menedżer.
2. Wybierz opcję **transakcja zwrotu** i wprowadź identyfikator paragonu przy użyciu skanowania kodu kreskowego lub za pomocą wpisu ręcznego. 
3. Umożliwia wybranie transakcji, która jest częścią zwrotu. 
4. Wybierz towary do zwrotu i wybierz metodę płatności.  
- Jeśli wybrana oferta płatności znajduje się na liście dozwolonych typów płatności zwrotnej, kasjer może dokończyć transakcję.
- Jeśli wybrana oferta płatności jest niedozwolona, zostanie wyświetlony komunikat o błędzie.
- Wybranie opcji **kwota należna** powoduje wyświetlenie listy wszystkich dozwolonych typów zwrotów płatności.

![Niedozwolone zwroty płatności](media/Return-policy-page6.png "Typ płatności zwrotu jest niedozwolony")



![Lista metod płatności](media/Return-policy-page5.PNG "Dozwolone typy płatności zwrotu")
