---
title: Konfigurowanie indeksu paliwowego przewoźnika
description: W tym przewodniku przedstawiono sposób tworzenia regionu indeksu paliwowego, indeksu paliwowego i indeksu paliwowego przewoźnika.
author: Weijiesa
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSFuelIndexRegion,TMSCarrierFuelIndexTable,TMSFuelIndex
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: weijiesa
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cb976369f9e8254f76a4de18df619d4420cf0538
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2022
ms.locfileid: "8672690"
---
# <a name="set-up-a-carrier-fuel-index"></a>Konfigurowanie indeksu paliwowego przewoźnika

[!include [banner](../../includes/banner.md)]

W tym przewodniku przedstawiono sposób tworzenia regionu indeksu paliwowego, indeksu paliwowego i indeksu paliwowego przewoźnika. Region indeksu paliwowego określa, do którego regionu powinien być stosowany indeks paliwowy, a indeks paliwowy określa cenę paliwa w określonym przedziale czasu. W celu odzwierciedlenia zmian w cenach paliwa w czasie można skojarzyć wiele indeksów paliwowych z przewoźnikiem.  Te zadania są zwykle wykonywane przez koordynatora transportu. Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.


## <a name="create-a-fuel-index-region"></a>Tworzenie regionu indeksu paliwowego
1. Wybierz kolejno opcje Zarządzanie transportem > Ustawienia > Indeksy paliwowe > Regiony indeksów paliwowych.
    * Najpierw należy utworzyć różne regiony, gdzie firma działa, i obliczyć różne dopłaty za paliwo.  
2. Kliknij przycisk Nowy.
3. W polu Region wpisz wartość.
4. W polu Nazwa wpisz wartość.
5. Kliknij przycisk Zapisz.

## <a name="create-a-fuel-index"></a>Tworzenie indeksu paliwowego
1. Wybierz kolejno opcje Zarządzanie transportem > Ustawienia > Indeksy paliwowe > Indeksy paliwowe.
    * Dla skonfigurowanych regionów należy wprowadzić bieżące ceny dla paliwa.  
2. Kliknij przycisk Nowy.
3. W polu Region kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
4. Na liście kliknij łącze w wybranym wierszu.
5. W polu Cena na galon wpisz liczbę.
6. W polu Obowiązująca data i godzina rozpoczęcia wprowadź datę i godzinę.
7. Kliknij przycisk Zapisz.

## <a name="create-a-carrier-fuel-index"></a>Tworzenie indeksu paliwowego przewoźnika
1. Wybierz kolejno opcje Zarządzanie transportem > Ustawienia > Indeksy paliwowe > Indeksy paliwowe przewoźnika.
2. Kliknij przycisk Nowy.
3. W polu Indeks paliwa przewoźnika wpisz wartość.
4. Wypełnij pole Opis.
5. Kliknij przycisk Nowy.
6. W polu Obowiązująca data i godzina rozpoczęcia wprowadź datę i godzinę.
7. W polu Cena na galon od wpisz liczbę.
    * W tym przykładzie w polu Cena na galon od ustawiono wartość 1,95.  
8. W polu Cena na galon do wpisz liczbę.
    * W tym przykładzie w polu Cena na galon do ustawiono wartość 2.  
9. W polu Wartość procentowa wpisz liczbę.
    * W tym przykładzie można ustawić procent 3.  
10. W polu Waluta kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
11. Na liście znajdź i zaznacz odpowiedni rekord.
12. Na liście kliknij łącze w wybranym wierszu.
13. Kliknij przycisk Zapisz.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]