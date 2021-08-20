---
title: Wprowadzanie umów sprzedaży
description: W tym temacie pokazano sposób tworzenia umowy sprzedaży, która zobowiązuje jednego odbiorcę do zakupu produktu na ustaloną kwotę w określonym czasie w zamian za specjalne rabaty.
author: omulvad
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesAgreementListPage, SalesAgreementCreate, SalesAgreement, InventItemIdLookupSimple, AgreementConfirmRunForm, SrsReportViewerForm, SalesAgreementCustomerReferencesPart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Service industries
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d074a68eb460725e96a986f9bc550add8e37b3b45d4a4879338fbe65a5e90c05
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6772431"
---
# <a name="enter-sales-agreements"></a>Wprowadzanie umów sprzedaży

[!include [banner](../../includes/banner.md)]

W tym temacie pokazano sposób tworzenia umowy sprzedaży, która zobowiązuje jednego odbiorcę do zakupu produktu na ustaloną kwotę w określonym czasie w zamian za specjalne rabaty. Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.


## <a name="set-up-sales-agreement-header"></a>Konfigurowanie nagłówka umowy sprzedaży
1. W okienku nawigacji przejdź do **Moduły > Sprzedaż i Marketing > Umowy sprzedaży > Umowy sprzedaży**.
2. Wybierz pozycję **Nowy**.
3. W polu **Konto odbiorcy** wybierz odpowiedni rekord z menu rozwijanego.
4. W polu **Klasyfikacja umowy sprzedaży** wybierz odpowiedni rekord z menu rozwijanego.
5. Rozwiń sekcję **Ogólne**.
6. W polu **Domyślne zobowiązanie** wybierz opcję **Zobowiązanie co do wartości produktu**. Typ zobowiązania to wymagane kryterium, które należy przypisać do umowy, aby zdefiniować sposób realizacji umowy. Cztery wstępnie zdefiniowane typy umożliwiają skonfigurowanie przedmiotu zobowiązania dla odbiorcy, wyrażonego jako ilość lub wartość. Zobowiązanie co do ilości można zastosować tylko do określonego produktu, ale typy oparte na wartości mają zastosowanie do sprzedaży produktów określonych i nieokreślonych.  
7. W polu **Data wygaśnięcia** ustaw przyszłą datę, kiedy umowa ma wygasnąć.
8. Kliknij przycisk **OK**.

## <a name="set-up-product-value-commitment-lines"></a>Konfigurowanie wierszy zobowiązania co do wartości produktu
1. Wybierz **Dodaj wiersz**.
2. W polu **Numer produktu** wybierz odpowiedni rekord z menu listy rozwijanej. Typ zobowiązania wybrany dla umowy wpływa na rodzaj informacji, które można wprowadzać w wierszach umowy. Na przykład w umowie opartej na wartości trzeba określić łączną kwotę netto (w uzgodnionej walucie), za którą odbiorca zobowiązuje się kupić towary od Twojej firmy. W tym przykładzie pol **Ilość** i **Jednostka** w wierszu są niedostępne, ponieważ tworzysz umowę dotycząca kupna produktów na określoną wartość przez odbiorcę.   
3. W polu **Kwota netto** wprowadź kwotę pieniężną, za jaką odbiorca zobowiązał się kupić.
4. W polu **Procent rabatu** wprowadź wartość procentową, która będzie stosowana do wierszy zamówienia sprzedaży odbiorcy połączonych z tą umową.
5. Rozwiń sekcję **Szczegóły wiersza**.
6. W polu **Wymuszono maks.** wybierz opcję **Tak**.
    - Wybór opcji **Wymuszono maks.** oznacza, że łączna ilość we wszystkich wierszach zamówienia sprzedaży, które używają specjalnych cen, rabatów i/lub warunków płatności zobowiązania, nie może przekraczać kwoty określonej w zobowiązaniu.  
    - Kwoty zwolnienia minimalna i maksymalna określają zakres wartości, na które należy wykonać sprzedaż w każdym zamówieniu sprzedaży korzystającym z wybranej umowy.   
7. Rozwiń sekcję **Nagłówek umowy sprzedaży**. Jeśli umowa ma stan inny niż **Obowiązuje**, zamówienia sprzedaży nie mogą być kojarzone z umową i w związku z tym nie mogą się przyczyniać do realizacji umowy. Stan można zmienić ręcznie na tym etapie. Jednak stan zazwyczaj zmienia się podczas potwierdzania umowy dla odbiorcy.  
8. W okienku akcji kliknij opcję **Umowa sprzedaży**.
9. Wybierz **Potwierdzenie**. Upewnij się, że w opcji **Oznaczenie umowy jako obowiązującej** zaznaczono wartość **Tak**.  
10. W polu **Drukuj raport** zaznacz opcję **Tak**.
11. Kliknij przycisk **OK**.
12. Zamknij stronę. Umowa jest teraz obowiązująca. Umowa teraz obowiązuje i można rozpocząć łączenie zamówień odbiorcy z umową w celu umożliwienia realizacji zadeklarowanego celu zakupowego.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]