---
title: Tworzenie zapotrzebowania wykorzystującego ZO
description: W tym temacie przedstawiono sposób dodawania informacji o cenie i dostawcy do zapotrzebowania na zakup z procesu ZO.
author: Henrikan
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqLineRelatedDocuments, EcoResCategorySingleLookup, PurchReqWorkflowDropDialog, WorkflowSubmitDialog, WorkflowStatus, WorkflowWorkItemActionDialog, WorkflowUserListLookup, PurchReqCopyRFQ, SysDataAreaSelectLookup, PurchRFQCaseTable, PurchRFQEditLines, PurchRFQReplyTable, UnitOfMeasureLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f88d50c24e84b94128aa3fd567562f3240832910
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7578063"
---
# <a name="create-a-requisition-that-uses-an-rfq"></a>Tworzenie zapotrzebowania wykorzystującego ZO

[!include [banner](../../includes/banner.md)]

W tym temacie przedstawiono sposób dodawania informacji o cenie i dostawcy do zapotrzebowania na zakup z procesu ZO. Przykład opisany w tym przewodniku można wykonać na danych firmy demonstracyjnej USMF. Aby wykonać wszystkie czynności, trzeba być zalogowanym jako administrator. Zadania w tym przewodniku zazwyczaj wykonują pracownicy działu zaopatrzenia.


## <a name="create-a-requisition"></a>Tworzenie zapotrzebowania
1. W okienku nawigacji wybierz kolejno **Moduły > Zaopatrzenie i sourcing > Zapotrzebowania na zakup > Zapotrzebowania na zakup przygotowane przeze mnie**.
2. Wybierz pozycję **Nowy**.
3. W polu **Nazwa** wpisz wartość.
4. W polu **Data wymagalności** wpisz datę.
5. W polu **Data księgowania** wpisz datę.
6. Kliknij przycisk **OK**.
7. W polu **Przyczyna** wprowadź lub wybierz wartość.
8. Wybierz **Dodaj wiersz**.
9. W polu **Kategoria zaopatrzenia** wybierz kategorię w drzewie, a następnie kliknij przycisk **OK**.
10. W polu **Nazwa produktu** wpisz wartość.
11. W polu **Ilość** wpisz liczbę.
12. W polu **Jednostka** wprowadź lub wybierz wartość.
13. Wybierz opcję **Zapisz**.
14. Wybierz opcję **Przepływ pracy**, aby otworzyć rozwijane okno dialogowe.
15. Wybierz opcję **Prześlij**.
16. Zamknij stronę.
17. Wybierz opcję **Prześlij**.

## <a name="reassign-a-workflow-task"></a>Zmiana przypisania zadania przepływu pracy
Następne zadanie polega na utworzeniu ZO w celu uzyskania od dostawców ofert na produkt. W danych firmy demonstracyjnej USMF przepływ pracy zapotrzebowania ma skonfigurowaną regułę, która stanowi, że jeśli dostawca nie zostanie wybrany lub cena jednostkowa dla wiersza jest równa 0, konkretnemu pracownikowi zostanie przypisane zadanie utworzenia ZO. Aby kontynuować pracę w tym przewodniku, musisz przypisać to zadanie innemu użytkownikowi (sobie). Możesz to zrobić tylko wtedy, gdy logujesz się jako administrator.  

1. Wybierz opcję **Przepływ pracy**, aby otworzyć rozwijane okno dialogowe.
2. Wybierz **Wyświetl historię**.
3. Odśwież stronę.
4. Rozwiń sekcję **Szczegóły śledzenia**.
5. W drzewie zaznacz wiersz, który zaczyna się fragmentem „Uruchomiono przepływ pracy dla pozycji dnia”.
6. Wybierz **Wyświetl szczegóły przepływu pracy**.
7. Rozwiń sekcję **Elementy robocze**.
8. Wybierz opcję **Przypisz ponownie**.
9. W polu **Użytkownik** wybierz opcję **Administrator**.
10. Wybierz opcję **Przypisz ponownie**.
11. Zamknij obie strony.

## <a name="create-an-rfq"></a>Tworzenie ZO

1. Odśwież stronę.
2. Wybierz **Zapytanie ofertowe**.
3. W polu **Firma dokonująca zakupu** zaznacz wartość **USMF**. Należy zaznaczyć tę samą firmę, jak w wierszu zapotrzebowania.  
4. Na liście oznacz wybrany wiersz. Jeśli masz wiele wierszy w zapotrzebowaniu na zakup, zaznacz wszystkie wiersze, które chcesz dodać do zapytania ofertowego.  
5. Kliknij przycisk **OK**.
6. Odśwież stronę.
7. Upewnij się, że pole informacji jest otwarte, a następnie rozwiń sekcję **Dokumenty powiązane**.
8. Kliknij łącze w polu **Zapytanie ofertowe** i otwórz ZO, które zostało właśnie utworzone.
9. Wybierz **Nagłówek**.
10. Wybierz opcję **Dodaj**.
11. W polu **Konto dostawcy** wprowadź lub wybierz wartość.
12. Wybierz opcję **Dodaj**.
13. W polu **Konto dostawcy** wprowadź lub wybierz wartość.
14. Wybierz opcję **Wyślij**.
15. Kliknij przycisk **OK**.
16. Wybierz opcję **Wprowadź odpowiedź**.
17. W okienku akcji kliknij pozycję **Odpowiedz**.
18. Wybierz **Kopiuj dane do odpowiedzi**. Spowoduje to skopiowanie danych, takich jak ilości i daty, z ZO do odpowiedzi.  
19. W polu **Cena jednostkowa** wpisz liczbę. Jest to cena otrzymana od dostawcy. Można także wprowadzić dodatkowe informacje od dostawcy.  
20. Wybierz **Akceptuj**.
21. Kliknij przycisk **OK**.

## <a name="verify-that-vendor-and-price-have-been-transferred-to-the-requisition"></a>Sprawdzanie, czy informacje o dostawcy i cenie zostały przeniesione do zapotrzebowania
1. Zamknij stronę.
2. Wybierz **Linie**.
3. Wybierz **Informacje pokrewne**.
4. Wybierz **Zapotrzebowanie na zakup**.
5. Zaznacz wiersz, który został przeniesiony do zapytania ofertowego. Sprawdź, czy informacje o cenie i dostawcy zostały skopiowane do zapotrzebowania.  
6. Wybierz opcję **Przepływ pracy**, aby otworzyć rozwijane okno dialogowe.
7. Wybierz opcję Zakończone.
8. Wybierz stronę.
9. Wybierz opcję Zakończone.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]