---
title: Konfigurowanie częstotliwości płatności
description: Microsoft Dynamics 365 Human Resources używa częstotliwości płatności do obliczania rocznego wynagrodzenia z tytułu świadczenia, określania kwoty składek na świadczenia płaconych przez pracownika w każdym okresie płacowym i definiowania częstotliwości płacenia dostawcom.
author: twheeloc
ms.date: 08/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0472e2203cc20fcf0904d22778092721b4cbce41
ms.sourcegitcommit: 66d129874635d34a8b29c57762ecf1564e4dc233
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/23/2022
ms.locfileid: "9323937"
---
# <a name="set-up-payment-frequencies"></a>Konfigurowanie częstotliwości płatności


Microsoft Dynamics 365 Human Resources używa częstotliwości płatności do obliczania rocznego wynagrodzenia z tytułu świadczenia, określania kwoty składek na świadczenia płaconych przez pracownika w każdym okresie płacowym i definiowania częstotliwości płacenia dostawcom.

W częstotliwościach płatności świadczeń są używane współczynniki konwersji do przeliczania okresów płatności świadczeń między miesięcznymi, półmiesięcznymi, dwutygodniowymi, tygodniowymi i dziennymi. Dzięki temu firmy mogą definiować współzależności między częstotliwościami płatności w ramach planu świadczeń.

Pola współczynników konwersji identyfikują przeliczniki z częstotliwości płatności na standardowe okresy płatności i umożliwiają systemowi wykonywanie obliczeń między częstotliwościami płatności. Kwota współczynnika konwersji określa również kwoty składki na świadczenie, którą pracownik powinien płacić w każdej częstotliwości płacenia.

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Częstotliwości płatności**.

2. Wybierz pozycję **Nowy**.

3. Określ wartości dla następujących pól:

   | Pole | Opis |
   | --- | --- |
   | **Częstotliwość płatności** | Unikatowa nazwa częstotliwości płatności. |
   | **Opis** | Opis częstotliwości płatności. |
   | **Okres** | Odpowiedni okres, który najlepiej pasuje do częstotliwości płacenia dostawcom świadczeń i pracownikom etatowym. Lista okresów składa się ze standardowych okresów płatności. |
   | **Liczba okresów płac** | Liczba okresów płacowych reprezentująca częstotliwość płacenia dostawcom świadczeń lub pracownikom. Ta kwota będzie używana do obliczania kwoty rocznego wynagrodzenia z tytułu świadczenie dla pracownika. |
   | **Roczny współczynnik konwersji** | Roczny współczynnik konwersji dla częstotliwości płatności. Na przykład roczny współczynnik konwersji dla miesięcznej częstotliwości wypłat wynosi: </br></br>(12 miesięcznych płatności / 1 rok) = 12 |
   | **Półroczny współczynnik konwersji** | Półroczny współczynnik konwersji dla częstotliwości płatności. Na przykład półroczny współczynnik konwersji dla miesięcznej częstotliwości wypłat wynosi: </br></br>(12 miesięcznych płatności / 2 razy w roku) = 6 |
   | **Kwartalny współczynnik konwersji** | Kwartalny współczynnik konwersji dla częstotliwości płatności. Na przykład kwartalny współczynnik konwersji dla miesięcznej częstotliwości wypłat wynosi: </br></br>(12 miesięcznych płatności / 4 kwartały) = 3 |
   | **Miesięczny współczynnik konwersji** | Miesięczny współczynnik konwersji dla częstotliwości płatności. Na przykład miesięczny współczynnik konwersji dla miesięcznej częstotliwości wypłat wynosi: </br></br>(12 miesięcznych płatności / 12 miesięcy) = 1 |
   | **Półmiesięczny współczynnik konwersji** | Półmiesięczny współczynnik konwersji dla częstotliwości płatności. Na przykład półmiesięczny współczynnik konwersji dla miesięcznej częstotliwości wypłat wynosi: </br></br>(12 miesięcznych płatności / 24 (2 razy w miesiącu)) = 0.5 | 
   | **Dwutygodniowy współczynnik konwersji** | Roczny współczynnik konwersji dla częstotliwości płatności. Na przykład roczny współczynnik konwersji dla miesięcznej częstotliwości wypłat wynosi: </br></br>(12 miesięcznych płatności / 26 tygodni) = 0,461538 |
   | **Tygodniowy współczynnik konwersji** | Roczny współczynnik konwersji dla częstotliwości płatności. Na przykład roczny współczynnik konwersji dla miesięcznej częstotliwości wypłat wynosi: </br></br>(12 miesięcznych płatności / 52 tygodnie) = 0,230769 |
   | **Dzienny współczynnik konwersji** | Roczny współczynnik konwersji dla częstotliwości płatności. Na przykład roczny współczynnik konwersji dla miesięcznej częstotliwości wypłat wynosi: </br></br>(12 miesięcznych płatności / 365 dni) = 0,032877 |
   | **Godzinowy współczynnik konwersji** | Roczny współczynnik konwersji dla częstotliwości płatności. Na przykład roczny współczynnik konwersji dla miesięcznej częstotliwości wypłat wynosi: </br></br>(12 miesięcznych płatności / 2080 godziny) = 0,005769

4. Wybierz opcję **Zapisz**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
