---
title: Tworzenie i przetwarzanie zgodności
description: Ten temat pokazuje jak przeprowadzić zarządzanie niezgodnościami na podstawie istniejącego zlecenia kontroli jakości.
author: perlynne
manager: tfehr
ms.date: 08/07/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4525e79cb388cc9bbcfe1d038a53cf53916a678c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5008102"
---
# <a name="create-and-process-a-conformance"></a>Tworzenie i przetwarzanie zgodności

[!include [banner](../../includes/banner.md)]

Ten temat pokazuje jak przeprowadzić zarządzanie niezgodnościami na podstawie istniejącego zlecenia kontroli jakości. To nagranie można uruchomić w kontekście firmy demonstracyjnej USMF i użyć sugerowanych wartości. Zazwyczaj ta procedura jest wykonywana przez pracownika ds. kontroli jakości.  Warunkiem wstępnym jest ukończenie instrukcji w [Sprawdzanie jakości towarów](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md). Aby wykonać zatwierdzenie niezgodności, użytkownik, który uruchomił nagranie zadania, musi mieć przypisaną wartość „Nazwa” na stronie Użytkownicy. Aby korzystać z notatek do dokumentu, użytkownik musi mieć również włączoną funkcję Obsługa dokumentu w opcjach użytkownika.


## <a name="select-a-quality-order"></a>Wybieranie zlecenia kontroli jakości
1. W okienku nawigacji otwórz **Moduły > Zarządzanie zapasami > Zadania okresowe > Zarządzanie jakością > Zlecenia kontroli jakości**.
2. Na liście wybierz zlecenie kontroli jakości, które zostało stworzone w [Sprawdzanie jakości towarów](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/master/articles/supply-chain/inventory/tasks/inspect-quality-goods.md).  

## <a name="create-a-nonconformance"></a>Tworzenie rekordu niezgodności
1. W okienku akcji wybierz pozycję **Zapytania**.
2. Wybierz **Niezgodności**.
3. Wybierz pozycję **Nowy**.
4. W menu rozwijanym pola **Typ problemu** wybierz problem, który został znaleziony podczas procesu inspekcji.  
5. Kliknij przycisk **OK**.

## <a name="approvereject-a-nonconformance"></a>Zatwierdzanie/odrzucanie rekordu niezgodności
1. Wybierz **Funkcje**.
2. Wybierz **Zatwierdź niezgodność**. W tym przykładzie zatwierdź niezgodność. Zatwierdzone niezgodności można skojarzyć z powiązanymi operacjami w celu zarejestrowania pracy wykonywanej w ramach postępowania z niezgodnością oraz, tak jak w tym temacie, przetwarzanie korekty.  
3. Wybierz opcję **Tak**.

## <a name="create-a-correction-action"></a>Tworzenie działania naprawczego
1. Wybierz **Korekty**.
2. Wybierz pozycję **Nowy**.
3. W polu **Numer pracownika** nowego wiersza wybierz żądany rekord z menu rozwijanego.
4. Kliknij opcję **Wybierz**.
5. Wybierz **Dołącz**. Utwórz notatkę dotyczącą korekty. W tym przykładzie działanie polega na skontaktowaniu się z dostawcą w celu omówienia przypadku niezgodności.  
6. Wybierz pozycję **Nowy**.
7. Wybierz **Uwaga**. Należy zauważyć, że w zależności od konfiguracji raportu mogą być drukowane różne typy dokumentów na raportach, które są związane z zarządzaniem niezgodnościami.  
8. W polu **Opis** wpisz wartość.
9. Zamknij stronę.

## <a name="maintain-a-correction"></a>Obsługa korekty
1. Wybierz opcję **Oznacz jako ukończone**.
2. Kliknij przycisk **OK**.
3. Zamknij stronę.

## <a name="close-a-nonconformance"></a>Zamykanie rekordu niezgodności
1. Wybierz **Funkcje**.
2. Wybierz **Zamknij tę niezgodność**.
3. Wybierz opcję **Tak**.
4. Zamknij strony.
