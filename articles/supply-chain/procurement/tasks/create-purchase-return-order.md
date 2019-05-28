---
title: Tworzenie zamówienia zwrotu zakupu
description: W tej procedurze pokazano, jak utworzyć zamówienie zwrotu zakupu przy użyciu akcji Faktura korygująca w celu skopiowania wierszy z dokumentu faktury od dostawcy do nowego zamówienia zakupu.
author: FrankDahl
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, PurchCopying, InventMarking, PurchEditLines
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e080252006d889e2f27db2bccb7b541f3ee4cf9e
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1547498"
---
# <a name="create-a-purchase-return-order"></a>Tworzenie zamówienia zwrotu zakupu

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano, jak utworzyć zamówienie zwrotu zakupu przy użyciu akcji Faktura korygująca w celu skopiowania wierszy z dokumentu faktury od dostawcy do nowego zamówienia zakupu. Ponadto pokazano sposób potwierdzania zamówienia i przetwarzania wysyłki towarów z powrotem do dostawcy. Przykład zawarty w tej procedurze można wykonać na danych firmy demonstracyjnej USMF. To zadanie zazwyczaj wykonuje pracownik działu zakupów.


## <a name="create-a-new-purchase-return-order"></a>Tworzenie nowego zamówienia zwrotu zakupu
1. Wybierz kolejno opcje Zaopatrzenie i sourcing > Zamówienia zakupu > Wszystkie zamówienia zakupu.
    * Pierwszym krokiem jest utworzenie nowego zamówienia zakupu, które ma być używane jako zamówienie zwrotu zakupu.  
2. Kliknij przycisk Nowy.
3. W polu Konto dostawcy wpisz wartość US-102.
4. Kliknij przycisk OK.
5. W okienku akcji kliknij pozycję Zakup.
6. Kliknij opcję Faktura korygująca.
    * To jest strona, na której możesz kopiować dane z istniejącej faktury od dostawcy do swojego zamówienia zwrotu. Ta sama strona jest używana dla innych akcji kopiowania. Jednak ponieważ została otwarta za pomocą operacji Faktura korygująca, jej konfiguracja wspiera tworzenie zamówienia zwrotu kompensującego faktury od dostawcy.  
7. Rozwiń sekcję Parametry.
    * Opcja Zmień znak jest zaznaczana automatycznie i nie można jej zmienić. Gwarantuje to, że znak zostanie zmieniony dla ilości, a dodane wiersze zamówienia skompensują fakturę od dostawcy.  
    * Opcja Kopiuj opłaty jest zaznaczana automatycznie i nie można jej zmienić. Oznacza to, że opłaty z faktury od dostawcy są dodawane do zamówienia zwrotu zakupu w celu skompensowania oryginalnej opłaty. Później można zmienić opłaty w nagłówku i wierszach zamówienia.  
    * Opcja Kopiuj dokładnie jest zaznaczana automatycznie i nie można jej zmienić. Gwarantuje to, że jest wykonywana dokładna kopia wartości we wszystkich polach nagłówka i wierszy faktury od dostawcy. Oznacza to, że zamówienie zwrotu zakupu jest tworzone z wartościami dokładnie odpowiadającymi wszystkim warunkom użytym w dokumencie faktury od dostawcy.  
    * Opcja Usuń wiersze zakupu powoduje usunięcie wszystkich wierszy zamówienia zakupu już istniejących w zamówieniu zakupu, a następnie dodanie nowych wierszy. W tym przykładzie jeszcze nie dodaliśmy żadnych wierszy do zamówienia zwrotu zakupu, tak że opcja nie przyniesie żadnego skutku. Tej opcji należy używać ostrożnie, ponieważ usuwa wszystkie istniejące wiersze bez dalszego ostrzeżenia.  
    * Opcja Kopiuj nagłówek zamówienia jest zaznaczana automatycznie i nie można jej zmienić. Gwarantuje to, że informacje są kopiowane z faktury od dostawcy i wprowadzane do nagłówka zamówienia zwrotu zakupu. Jest to przydatne, ponieważ pomaga zapewnić, że zamówienie zwrotu zakupu kompensuje fakturę przy użyciu podobnych warunków.  
8. Zwiń sekcję Parametry.
9. Rozwiń sekcję Faktury.
    * Strona została otwarta za pomocą akcji Faktura korygująca, więc jedyną dostępną opcją jest kopiowanie informacje z faktur od dostawców. Ta karta pokazuje wszystkie faktury dostępne dla konta dostawcy określonego w utworzonym wcześniej zamówieniu zwrotu zakupu.   Faktury są identyfikowane za pomocą załącznika faktury lub identyfikatora zamówienia zakupu.  
10. Odszukaj fakturę dostawcy identyfikowaną przez numer faktury AP-0006 i zaznacz ten wiersz, klikając w nim dowolne pole.
11. Zaznacz wiersz, klikając jego pole wyboru. 
    * Zwróć uwagę, że wiersze dostępne w fakturze od dostawcy zostały zaznaczone automatycznie razem z zamówieniem. Ta konkretna faktura od dostawcy ma 2 wiersze zamówienia. W tym przykładzie zwrócimy część ilości określonej w drugim wierszu.  
12. Zaznacz drugi wiersz (ten z towarem M0006), klikając jego dowolne pole.
13. W polu Ilość zmień ilość na 10. Jest to ilość, która zostanie zwrócona do dostawcy. 
14. Zaznacz pierwszy wiersz (ten z towarem M0005), klikając jego dowolne pole.
15. Wyczyść pole wyboru tego wiersza.
    * Do zamówienia zostaną skopiowane tylko wybrane przez Ciebie wiersze.  
16. Zwiń sekcję Faktury.
17. Rozwiń sekcję Wybrane wiersze lub nagłówek do skopiowania.
    * Ten widok zawiera zestawienie wszystkich dokumentów i wierszy, które zostały wybrane do skopiowania do zamówienia.  
18. Zwiń sekcję Wybrane wiersze lub nagłówek do skopiowania.
19. Kliknij przycisk OK.
    * Wybrany wiersz został skopiowany do zamówienia zwrotu zakupu. Pole Ilość pokazuje wartość -10.   
20. Kliknij opcję Zapasy.
21. Kliknij opcję Zaznaczanie.
    * Utworzony wiersz zamówienia został oznaczony względem transakcji magazynowej z faktury dostawcy. Gwarantuje to, że do dostawcy są zwracane te same zapasy, które przyjęto od niego wcześniej. Istnieje kilka sytuacji, gdy oznaczanie nie następuje, na przykład jeśli zapasy zostały już oznaczone jako zużyte albo jeśli produkt nie wymaga oznaczania.  
22. Kliknij przycisk OK.

## <a name="confirm-and-record-the-shipment-of-goods"></a>Potwierdzanie i rejestrowanie wysyłki towarów
1. Kliknij przycisk Potwierdź.
2. W okienku akcji kliknij pozycję Odbierz.
3. Kliknij opcję Dokument przyjęcia produktów.
    * Ta strona służy do rejestrowania dokumentu przyjęcia produktów dla zamówień zakupu, a także do przetwarzania zwrotu towarów do dostawcy. Wiersze zamówienia z ujemną ilością oznaczają, że towary mają zostać zwrócone do dostawcy, a dokument wygenerowany na tej stronie może być używany jako dokument dostawy dla tego zwrotu.   
    * W tym przykładzie w polu Ilość wybierz opcję Ilość zamówiona.   Gwarantuje to, że wysyłka będzie przetwarzana dla pełnej zamówionej ilości, z którą utworzono wiersze zamówienia.   
4. W polu Dokument przyjęcia produktów wpisz wartość.
    * To pole służy do wprowadzania odwołania, które będzie używane jako załącznik dla arkusza dokumentu przyjęcia produktów.  
5. Kliknij przycisk OK.
    * Towary zostały teraz zarejestrowane jako wysłane w zamówieniu zwrotu zakupu oraz utworzono arkusz dokumentu przyjęcia produktów. Można użyć akcji Dokument przyjęcia produktów, aby przejrzeć arkusze utworzone z zamówieniem zakupu i sprawdzić, co zostało przyjęte lub zwrócone i kiedy.  

