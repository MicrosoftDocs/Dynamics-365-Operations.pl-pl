---
title: Liczenie zapasów w magazynie
description: W tym temacie opisano proces tworzenia i księgowania arkusza inwentaryzacji zapasów w celu policzenia określonego towaru w lokalizacji w magazynie.
author: MarkusFogelberg
manager: tfehr
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCreate, HcmWorkerLookUp, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 452822eaf26c26e4c9e00f909dbd18127f6fc781
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5230111"
---
# <a name="count-inventory-in-a-warehouse"></a>Liczenie zapasów w magazynie

[!include [banner](../../includes/banner.md)]

W tym temacie opisano proces tworzenia i księgowania arkusza inwentaryzacji zapasów w celu policzenia określonego towaru w lokalizacji w magazynie. Procedura dotyczy funkcji „podstawowego magazynowania” dostępnej w module Zarządzanie zapasami, a nie funkcji magazynowania dostępnej w module Zarządzanie magazynem. Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych. Jeśli korzystasz z własnych danych, upewnij się, że masz skonfigurowane produkty i lokalizacje oraz utworzony arkusz magazynowy dla arkuszy inwentaryzacji. Inwentaryzacja jest zwykle przeprowadzana przez pracownika magazynu.


## <a name="create-an-inventory-counting-journal"></a>Tworzenie arkusza inwentaryzacji zapasów
1. Przejdź do menu **Okienko nawigacji > Moduły > Zarządzanie zapasami > Wpisy w arkuszu > Zliczanie towarów > Inwentaryzacja**.
2. Wybierz pozycję **Nowy**.
3. W polu **nazwa** wybierz z listy rozwijanej nazwę arkusza inwentaryzacji zapasów, którego chcesz użyć. Niektóre inne pola zostaną wypełnione zgodnie z ustawieniami wybranego arkusza inwentaryzacji zapasów.  
4. W polu **Pracownik** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
5. Na liście **zaznacz** pracownika, z którego chcesz skorzystać.
6. Kliknij przycisk **OK**.

## <a name="create-journal-lines"></a>Utwórz wiersze arkusza
1. Wybierz pozycję **Nowy**.
2. W polu **Numer produktu** wybierz odpowiedni rekord z listy rozwijanej. Jeśli używasz danych firmy demonstracyjnej USMF, wybierz opcję **A0001**.  
3. W polu **Oddział** wybierz odpowiedni rekord z listy rozwijanej. Jeśli używasz danych firmy demonstracyjnej USMF, wybierz oddział **2**.
4. W polu **Magazyn** wybierz odpowiedni rekord z listy rozwijanej. Jeśli używasz danych firmy demonstracyjnej USMF, wybierz magazyn **24**.  
5. W polu **Lokalizacja** wybierz odpowiedni rekord z listy rozwijanej. Jeśli używasz danych firmy demonstracyjnej USMF, wybierz lokalizację **BULK-001**.  
6. W polu Policzono wprowadź liczbę. Jeśli wprowadzisz zliczoną liczbę inną niż liczba widoczna w polu **Dostępne zapasy**, pole **Ilość** zostanie zaktualizowane w celu pokazania niezgodności.  
7. Wybierz opcję **Zapisz**.

## <a name="post-the-inventory-counting-journal"></a>Księgowanie arkusza inwentaryzacji zapasów
1. Wybierz opcję **Zaksięguj**. Jeśli podczas księgowania arkusza inwentaryzacji zapasów zliczona ilość jest inna niż ilość podana w polu **Dostępne zapasy**, nastąpi zaksięgowanie przyjęcia na magazyn lub wydania, zmiana poziomu i wartości zapasów oraz wygenerowanie transakcji finansowych.
2. Kliknij przycisk **OK**.

## <a name="view-inventory-transactions"></a>Wyświetlanie transakcji magazynowych
1. Wybierz **Zapasy**.
2. Wybierz **transakcje**. Tutaj można zobaczyć wszystkie powiązane transakcje, które zostaną utworzone podczas księgowania arkusza inwentaryzacji zapasów.   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]