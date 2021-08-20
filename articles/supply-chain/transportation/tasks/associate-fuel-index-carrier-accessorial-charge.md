---
title: Kojarzenie indeksu paliwa z przewoźnikiem jako opłaty za usługi dodatkowe
description: W tym podręczniku pokazano sposób tworzenia przypisania usług dodatkowych, opłaty za usługi dodatkowe przewoźnika i danych głównych usług dodatkowych dla dopłaty za paliwo, a także kojarzenia indeksu paliwowego przewoźnika z przewoźnikiem.
author: ShylaThompson
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSRatingProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f1288867dbfee12f0fd50550aa8974d692ac271bb4b6bdbbd1e2423cd8d3413a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6756033"
---
# <a name="associate-a-fuel-index-with-a-carrier-as-an-accessorial-charge"></a>Kojarzenie indeksu paliwa z przewoźnikiem jako opłaty za usługi dodatkowe

[!include [banner](../../includes/banner.md)]

W tym podręczniku pokazano sposób tworzenia przypisania usług dodatkowych, opłaty za usługi dodatkowe przewoźnika i danych głównych usług dodatkowych dla dopłaty za paliwo, a także kojarzenia indeksu paliwowego przewoźnika z przewoźnikiem. Przed wykonaniem zadań z tego przewodnika należy utworzyć indeks paliwowy przewoźnika. Do tego celu służy przewodnik „Konfigurowanie indeksu paliwowego przewoźnika”. Te zadania konfiguracyjne z reguły są wykonywane przez menedżera logistyki. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.


## <a name="create-an-accessorial-master"></a>Tworzenie danych głównych usług dodatkowych
1. Wybierz kolejno opcje Zarządzanie transportem > Ustawienia > Ocena > Główne usługi dodatkowe.
2. Kliknij przycisk Nowy.
3. W polu Główne dodatkowe usługi wpisz wartość.
4. W polu Nazwa wpisz wartość.
5. Kliknij przycisk Zapisz.

## <a name="create-a-carrier-accessorial-charge"></a>Tworzenie opłaty za usługi dodatkowe przewoźnika
1. Wybierz kolejno opcje Zarządzanie transportem > Ustawienia > Ocena > Opłaty za usługi dodatkowe przewoźnika.
2. Kliknij przycisk Nowy.
3. W polu Identyfikator współpracownika przewoźnika wpisz wartość.
4. W polu Firma przewozowa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
5. Na liście znajdź i zaznacz odpowiedni rekord.
    * W tym przykładzie wybierz opcję Przewoźnik ciężarowy.  
6. Na liście kliknij łącze w wybranym wierszu.
7. W polu Usługa przewozowa kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
8. Na liście kliknij łącze w wybranym wierszu.
9. W polu Główne dodatkowe usługi kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
10. Na liście znajdź i zaznacz odpowiedni rekord.
    * W tym przykładzie wybierz nowo utworzone dane główne usług dodatkowych.  
11. Kliknij przycisk Zapisz.

## <a name="create-an-accessorial-assignment"></a>Tworzenie przypisania usług dodatkowych
1. Kliknij opcję Przypisania usług dodatkowych.
2. Kliknij przycisk Nowy.
3. W polu Nazwa wpisz wartość.
4. Przełącz rozwinięcie sekcji Kryteria.
    * W kryteriach można określić, aby dopłata za paliwo była stosowana zawsze, lub — jak w tym przykładzie — że ma dotyczyć tylko określonego regionu.  
5. W polu Początkowy kod pocztowy wpisz wartość.
6. W polu Końcowy kod pocztowy wpisz wartość.
7. Przełącz rozwinięcie sekcji Obliczanie.
    * W sekcji obliczeń można określić sposób obliczania dopłaty za paliwo. To obliczenie zależy od jednostki usług dodatkowych wybranej jako podstawa do obliczeń.  
8. W polu Typ opłaty za usługi dodatkowe wybierz opcję „Dopłata za paliwo”.
9. W polu Jednostka usług dodatkowych wybierz opcję „Przebieg”.
10. W polu Region kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
11. Na liście kliknij łącze w wybranym wierszu.
12. Kliknij przycisk Zapisz.

## <a name="update-the-carrier-rating-profile"></a>Aktualizowanie profilu wyznaczania stawek przewoźnika
1. Wybierz kolejno opcje Zarządzanie transportem > Ustawienia > Przewoźnicy > Firmy przewozowe.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. Przełącz rozwinięcie sekcji Profile oceny.
4. Kliknij przycisk Edytuj.
5. W polu Indeks paliwa przewoźnika kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
6. Na liście kliknij łącze w wybranym wierszu.
7. Kliknij przycisk Zapisz.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]