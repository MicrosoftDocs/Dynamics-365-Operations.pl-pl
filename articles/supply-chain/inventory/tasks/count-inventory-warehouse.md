---
title: Liczenie zapasów w magazynie
description: W tym artykule opisano proces tworzenia i księgowania arkusza inwentaryzacji zapasów w celu policzenia określonego towaru w lokalizacji w magazynie.
author: yufeihuang
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCreate, HcmWorkerLookUp, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7c8712b88867dc4be48bbdb4b905993e3ccbc73f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8870645"
---
# <a name="count-inventory-in-a-warehouse"></a>Liczenie zapasów w magazynie

[!include [banner](../../includes/banner.md)]

W tym artykule opisano proces tworzenia i księgowania arkusza inwentaryzacji zapasów w celu policzenia określonego towaru w lokalizacji w magazynie. Procedura dotyczy funkcji „podstawowego magazynowania” dostępnej w module Zarządzanie zapasami, a nie funkcji magazynowania dostępnej w module Zarządzanie magazynem. Można przejść tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych. Jeśli korzystasz z własnych danych, upewnij się, że masz skonfigurowane produkty i lokalizacje oraz utworzony arkusz magazynowy dla arkuszy inwentaryzacji. Inwentaryzacja jest zwykle przeprowadzana przez pracownika magazynu.


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