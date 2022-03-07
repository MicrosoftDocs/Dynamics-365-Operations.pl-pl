---
title: Konfiguracje sklepu dla zestawień sieci sprzedaży
description: Ta procedura prowadzi przez konfiguracje sprzedaży sklepu sieci sprzedaży, które mają wpływ na sposób tworzenia i księgowana zestawień Commerce.
author: jashanno
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: af4321cd9d6e15c82c4eef1f1ca218b8301ebf35
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5003660"
---
# <a name="store-configurations-for-retail-statements"></a>Konfiguracje sklepu dla zestawień sieci sprzedaży

[!include [banner](../includes/banner.md)]

Ta procedura prowadzi przez konfiguracje sprzedaży sklepu sieci sprzedaży, które mają wpływ na sposób tworzenia i księgowana zestawień Commerce. Wymiary finansowe w sklepach są omówione w innej procedurze. Ta procedura wykorzystuje firmę demonstracyjną USRT.

1. W **okienku nawigacji** kliknij kolejno opcje **Moduły > Retail i Commerce > Kanały > Sklepy > Wszystkie sklepy**.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. Na liście kliknij łącze w wybranym wierszu.
4. Kliknij przycisk **Edytuj**.
5. Ustawienia w skróconej karcie **Zestawienie/zamknięcie** wpływają na tworzenie, sprawdzanie poprawności i księgowanie zestawień dla sklepu. Rozwiń skróconą kartę **Zestawienie/zamknięcie**.  
6. W polu **Metoda zestawienia** wybierz metodę, której chcesz używać do grupowania wierszy zestawienia.  
7. Wybierz opcję „Tak” w **Jedno zestawienie na dzień**, jeśli ma być tworzone tylko jedno zestawienie dziennie podczas wykonywania zadania wsadowego tworzenia zestawień.  
8. Pole **Obliczenia deklaracji środków płatniczych** określa, czy deklaracje środków płatniczych powinny być dodawane razem czy też ma być używana ostatnia deklaracja.  
9. W polu **Zaokrąglanie** wybierz konto księgowe do księgowania różnic zaokrągleń.  
10. W polu **Maksymalna różnica zaokrągleń** można wprowadzić maksymalną dozwoloną różnicę zaokrąglenia.
11. W polu **Księgowanie** można wprowadzić maksymalną łączną rozbieżność księgowania dozwoloną dla zestawienia.
12. W polu **Zmiana** można wprowadzić maksymalną łączną rozbieżność dozwoloną w granicach zmiany w zestawieniu.  
13. W polu **Transakcja** można wprowadzić maksymalną łączną rozbieżność dozwoloną w wierszu zestawienia.  
14. W polu **Metoda zamknięcia** można określić, czy transakcje, które zostaną uwzględnione w zestawieniu, powinny być częścią zamkniętej zmiany czy też mogą być dowolnymi transakcjami o zdefiniowanym zakresie daty/godziny.  
15. W polu **Koniec dnia roboczego** można wprowadzić godzinę, jeśli transakcje zachodzące po północy mają być księgowane w poprzednim dniu.  
16. Wybierz opcję „Tak” w **Księguj z dniem roboczym**, jeśli transakcje zachodzące po północy mają być księgowane jako część poprzedniego dnia.  
17. Wybierz opcję „Tak” w **Podziel wg metody zestawienia** , aby zestawienia były tworzone dla każdej zdefiniowanej metody wykonywania zestawień. To działanie może być przydatne, jeśli wydajność księgowania wymaga poprawy dla sklepów o dużym wolumenie transakcji, ponieważ spowoduje to utworzenie wielu mniejszych zestawień, które mogą być przetwarzane jednocześnie.  
18. Na karcie skróconej **Ogólne** w polu **Domyślny odbiorca** można wybrać konto odbiorcy na potrzeby sprzedaży klientom przypadkowym.  

