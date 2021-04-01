---
title: Przypisywanie szablonu faktury niezależnej do odbiorcy
description: To zadanie przedstawia sposób przypisywania szablonu faktury niezależnej do odbiorcy.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, CustRecurrenceInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d1f87c731a603dbb3def0ebc2d2ebe54f9706053
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254127"
---
# <a name="assign-a-free-text-invoice-template-to-a-customer"></a>Przypisywanie szablonu faktury niezależnej do odbiorcy

[!include [banner](../../includes/banner.md)]

To zadanie przedstawia sposób przypisywania szablonu faktury niezależnej do odbiorcy. To zadanie wykorzystuje firmę demonstracyjną USMF i jest przeznaczone dla użytkownika, który odpowiada za zarządzanie i przetwarzanie faktur dla odbiorców.

1. W **okienku nawigacji** otwórz **Moduły > Rozrachunki z odbiorcami > Odbiorcy > Wszyscy odbiorcy**.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. W **okienku akcji** kliknij pozycję **Faktura**.
4. Kliknij opcję **Faktury cykliczne**. Ta strona służy do przypisania szablonów faktur niezależnych do odbiorców oraz określania, jak często faktury będą wysyłane do odbiorców.  
5. Kliknij przycisk **Nowy**, aby przypisać nowy szablon do odbiorcy.
6. W polu **Szablon** zaznacz szablon faktury niezależnej, który chcesz przypisać odbiorcy.
7. Na liście znajdź i zaznacz odpowiedni rekord.
8. Na liście kliknij łącze w wybranym wierszu.
9. W polu **Data rozpoczęcia fakturowania** wprowadź datę, kiedy zostanie wygenerowana pierwsza faktura.
10. W sekcji **Koniec cyklu** wprowadź cykliczną datę zakończenia.  
    * Wybierz jedną z następujących opcje: Brak daty zakończenia — Faktury będą generowane bezterminowo do czasu usunięcia szablonu z konta odbiorcy.
    * Data zakończenia fakturowania — Zaznacz tę opcję i wprowadź ostatni dzień, w którym fakturę można wygenerować.  
11. W polu **Maksymalna kwota skumulowana** wprowadź maksymalną skumulowaną kwotę, po której zostanie zatrzymane tworzenie faktury. Wprowadź maksymalną kwotę skumulowaną, jaką można osiągnąć za pomocą wybranego szablonu. Na przykład wprowadzenie wartości 1 000,00 i generowanie faktur miesięcznych dla każdej kwoty 100,00 spowoduje, że faktury przestaną być generowane po wygenerowaniu dziesiątej faktury.  
12. W sekcji **Generuj cykliczne faktury przy użyciu wartości domyślnych** wybierz szablon faktury niezależnej lub konto odbiorcy. Umożliwia określenie, czy ma być używany szablon faktury niezależnej czy konto odbiorcy do określania wartości domyślnych języka, profilu księgowania, grupy podatków, grupy podatków towaru, kodu listy, kraju/regionu dostawy, waluty, warunków płatności, metody płatności, specyfikacji płatności, harmonogramu płatności, rabatu gotówkowego, wymiarów finansowych oraz przekazu GIRO podczas tworzenia faktur.  
13. W polu **Wzorzec cyklu** wybierz wzorzec cyklu.
    + Dziennie — Wybierz tę opcję i podaj liczbę dni w polu Na. Na przykład, jeśli zostanie wprowadzona wartość 15, co 15 dni będzie generowana faktura dla tego odbiorcy.
    + Tygodniowo — Wybierz tę opcję i podaj liczbę tygodni w polu Na. Na przykład, jeśli zostanie wprowadzona wartość 2, co 2 tygodnie będzie generowana faktura dla tego odbiorcy.
    + Miesięcznie — Wybierz tę opcję i podaj liczbę miesięcy w polu Na. Na przykład, jeśli zostanie wprowadzona wartość 6, co 6 miesięcy będzie generowana faktura dla tego odbiorcy.
    + Rocznie — Wybierz tę opcję i podaj liczbę lat w polu Na. Na przykład, jeśli zostanie wprowadzona wartość 2, co 2 lata będzie generowana faktura dla tego odbiorcy.  
14. W polu **Na** wprowadź liczbę.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]