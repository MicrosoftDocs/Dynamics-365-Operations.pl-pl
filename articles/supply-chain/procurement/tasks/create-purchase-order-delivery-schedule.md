---
title: Tworzenie zamówienia zakupu z harmonogramem dostaw
description: W tym temacie pokazano sposób tworzenia harmonogramu dostaw dla zamówienia zakupu.
author: Henrikan
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, InventItemIdLookupPurchase, PurchDeliverySchedule, PurchEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 670870df1b0fcd86a0f04ce454e6ef84187187b8
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7566942"
---
# <a name="create-a-purchase-order-with-a-delivery-schedule"></a>Tworzenie zamówienia zakupu z harmonogramem dostaw

[!include [banner](../../includes/banner.md)]

W tym temacie pokazano sposób tworzenia harmonogramu dostaw dla zamówienia zakupu. Harmonogram dostaw jest używany w reakcji na żądanie dostarczenia ilości z zamówienia lub arkusza w kilku dostawach. Przykład zawarty w tym przewodniku można wykonać na danych firmy demonstracyjnej USMF. Zazwyczaj procedurę wykonuje pracownik działu zakupów.

## <a name="create-a-delivery-schedule"></a>Tworzenie harmonogramu dostaw
1. W okienku nawigacji wybierz kolejno **Moduły > Zaopatrzenie i sourcing > Zamówienia zakupu > Wszystkie zamówienia zakupu**.
2. W okienku akcji wybierz opcję **Nowy**.
3. W polu **Konto dostawcy** wpisz wartość `US-101`.
4. Kliknij przycisk **OK**.
5. W polu **Numer pozycji** wpisz `M0001`.
6. W polu **Ilość** wpisz wartość `10`.
7. Wybieranie **Wiersz zamówienia zakupu**.
8. Wybierz **Harmonogram dostaw**.
- Na stronie **Harmonogram dostaw** można określić liczbę wysyłek, w jakiej łączna ilość z wiersza zamówienia zostanie dostarczona od dostawcy.  
- Domyślnie system kopiuje łączną ilość i inne szczegóły dostawy z oryginalnego wiersza zakupu do pierwszego wiersza harmonogramu dostawy. W tym przykładzie utworzymy harmonogram dla dwóch wysyłek, gdzie data drugiej wysyłki będzie przesunięta o tydzień względem daty pierwszej dostawy.  
9. W polu **Ilość** zmień ilość na `4`.
10. Wybierz pozycję **Nowy**.
11. W polu **Ilość** wprowadź `6` jako pozostałą ilość.
- W polu Data dostawy wybierz datę, która jest późniejsza o tydzień niż data w pierwszym wierszu dostawy.  
- Ilość całkowitą przydzieloną do wierszy harmonogramu dostaw można śledzić w polach **Razem** i **Pozostałe**. Jeśli pozostała ilość wynosi zero, cała ilość z oryginalnego wiersza została przydzielona do harmonogramu.  
12. Rozwiń sekcję **Konwersja opłat**.
- Opcje dostępne w tym miejscu umożliwiają kontrolowanie sposobu rozdziału opłat między wiersze harmonogramu dostaw. Jeśli wybierzesz opcję **Kopiuj kwoty brutto**, kwota opłaty z oryginalnego wiersza zamówienia zostanie skopiowana do każdego wiersza dostawy. Opcja **Przenieś do wierszy dostawy** dzieli opłatę z oryginalnego wiersza zgodnie z ilością w każdym wierszu dostawy.  
13. Zwiń sekcję **Konwersja opłat**.
14. Kliknij przycisk **OK**.
- Harmonogram dostaw jest teraz zastosowany do zamówienia.  
- Oryginalny wiersz zamówienia, nazywany teraz wierszem handlowym, został przekonwertowany na wiersz zamówienia z wieloma dostawami. Jest oznaczony specjalną ikoną i pełni rolę nagłówka wierszy dostawy.  
15. Zaznacz drugi wiersz zamówienia, czyli pierwszy z dwóch wierszy dostaw.
- Te dwa nowe wiersze, nazywane wierszami dostawy, tworzą jeden harmonogram dostaw. Zamówienie będzie przetwarzane dla tych wierszy, a nie dla oryginalnego wiersza. Jeśli są drukowane dokumenty takie jak potwierdzenia, arkusze dokumentów przyjęcia produktów lub faktury, wyświetlane są tylko wiersze dostaw.  

## <a name="change-the-delivery-schedule"></a>Zmiana harmonogramu dostaw
Można zmienić ilość w wierszach dostawy. Po wykonaniu tej czynności wiersz handlowy zostanie automatycznie zaktualizowany o całkowitą ilość z wierszy dostaw.  
1. W polu **Ilość** w pierwszym wierszu dostawy zmień ilość z `4` na `5`.
2. Zaznacz pierwszy wiersz zamówienia (wiersz handlowy).  
- Ilość w wierszu handlowym została zmieniona na 11.  

## <a name="process-product-receipt-using-delivery-schedules"></a>Przetwarzanie przyjęcia produktów przy użyciu harmonogramów dostaw
Przed przetwarzaniem przyjęcia produktów należy potwierdzić zamówienie zakupu. W takim przykładzie przyjęcie jest rejestrowane bezpośrednio w zamówieniu zakupu. Przyjęcie można było również zarejestrować po dostarczeniu towarów do magazynu.  
1. W okienku akcji wybierz **Zakup**.
2. Wybierz opcję **Potwierdź**.
3. W okienku akcji wybierz pozycję **Odbierz**.
4. Wybierz pozycję **Przyjęcie produktu**. W polu **Dokument przyjęcia** produktów wpisz dowolną wartość.
- To pole służy do wprowadzania odwołania, które będzie używane jako załącznik dla arkusza dokumentu przyjęcia produktów.  
- W polu **Ilość** zaznacz opcję **Ilość zamówiona**. Ta opcja oznacza, że przyjęcie będzie przetwarzane dla ilości, z którą utworzono wiersze zamówienia.  
- Upewnij się, że w polu **Drukuj dokument przyjęcia produktów** zaznaczono wartość **Nie**. W tym przykładzie drukowanie nie jest potrzebne.  
5. Rozwiń sekcję **Wiersze**.
- Zwróć uwagę, że dokument przyjęcia produktów został utworzony dla dwóch wierszy dostawy, a nie oryginalnego wiersza zamówienia. Gdyby przyjęcie zostało zarejestrowane w magazynie, zostałoby również zarejestrowane w wierszach harmonogramu dostaw.  
6. Zwiń sekcję **Wiersze**.
7. Wybierz **OK**, aby zaksięgować przyjęcie.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]