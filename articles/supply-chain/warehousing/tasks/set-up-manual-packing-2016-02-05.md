--- 
title: "Konfigurowanie pakowania ręcznego (tylko luty i maj 2016)"
description: "Proces pakowania umożliwia sprawdzenie poprawności produktów i ich zapakowanie do kontenerów."
author: BibiSp
manager: AnnBe
ms.date: 11/04/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 7f992a6a1655cd868d79228c490d59b46bfae715
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-manual-packing-february--may-2016-only"></a>Konfigurowanie pakowania ręcznego (tylko luty i maj 2016)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Proces pakowania umożliwia sprawdzenie poprawności produktów i ich zapakowanie do kontenerów. W tym procesie pracownicy magazynu pobierają produkty z lokalizacji przechowywania i przenoszą je do stacji pakowania, gdzie sprawdzają typy i ilości towarów oraz przypisują je do odpowiednich kontenerów. Jeśli kontener jest całkowicie zapakowany, pracownicy mogą go zamknąć i przenieść do doków załadunkowych, skąd produkty są gotowe do wysyłki. Ta procedura wykorzystuje firmę demonstracyjną USMF.


## <a name="set-up-location-profiles"></a>Ustaw profile lokalizacji
1. Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Magazyn > Profile lokalizacji.
2. Kliknij przycisk Nowy.
    * Profil lokalizacji jest używany w stacjach pakowania. Zawiera informacje i reguły dotyczące lokalizacji.  
3. W polu Identyfikator profilu lokalizacji wpisz wartość.
4. W polu Nazwa wpisz wartość.
5. W polu Format lokalizacji wprowadź lub wybierz wartość.
6. W polu Typ lokalizacji wprowadź lub wybierz wartość.
7. W polu Pozwól na mieszane pozycje wybierz opcję Tak.
8. W polu Pozwól na mieszane stany zapasów wybierz opcję Tak.
9. W polu Zastąp reguły dla dni partii wybierz opcję Tak.
10. Zamknij stronę.

## <a name="set-up-warehouse-management-parameters"></a>Konfigurowanie parametrów zarządzania magazynem 
1. Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Parametry zarządzania magazynem.
2. Kliknij kartę Opakowanie.
3. W polu Identyfikator profilu lokalizacji pakowania wprowadź lub wybierz wartość.
    * Zaznacz profil lokalizacji, którego chcesz używać do pakowania.  
4. Zamknij stronę.

## <a name="set-up-container-types"></a>Konfigurowanie typów kontenerów
1. Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Kontenery > Typy kontenerów.
2. Kliknij przycisk Nowy.
    * Można zdefiniować typy kontenerów, które mają być używane. Można określić wymiary fizyczne kontenera, w tym tarę, maksymalną wagę, maksymalną objętość, długość, szerokość i wagę.  Atrybuty są konfigurowalnymi polami, które umożliwiają dodawanie kolejnych wymiarów do typu kontenera.     
3. W polu Kod typu kontenera wpisz wartość.
4. Wypełnij pole Opis.
5. W polu Waga tara wpisz liczbę.
6. W polu Maksymalna waga wpisz liczbę.
7. W polu Objętość wpisz liczbę.
8. W polu Długość wpisz liczbę.
9. W polu Szerokość wprowadź liczbę.
10. W polu Wysokość wprowadź liczbę.
11. Kliknij przycisk Zapisz.
12. Zamknij stronę.

## <a name="set-up-packing-profiles"></a>Konfigurowanie profili pakowania
1. Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Opakowanie > Profile pakowania.
2. Kliknij przycisk Nowy.
3. W polu Identyfikator profilu pakowania wpisz wartość.
4. Wypełnij pole Opis.
5. W polu Identyfikator profilu zamknięcia kontenera wprowadź lub wybierz wartość.
    * Identyfikator profilu zamknięcia kontenera jest opcjonalny i pełni rolę domyślnego profilu zamknięcia kontenera dla tego profilu opakowania.  
6. W polu Tryb identyfikatora kontenera wybierz opcję.
    * Ta opcja decyduje, czy identyfikator kontenera będzie automatycznie generowany podczas tworzenia kontenera czy też będzie generowany ręcznie.  
7. W polu Typ kontenera wprowadź lub wybierz wartość.
    * Typ kontenera będzie używany domyślnie podczas tworzenia nowego kontenera.  
8. Zaznacz pole wyboru Automatycznie twórz kontener podczas zamykania kontenera.
9. Kliknij przycisk Zapisz.
10. Zamknij stronę.

## <a name="set-up-container-closing-profiles"></a>Konfigurowanie profili zamknięcia kontenera
1. Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Kontenery > Profile zamknięcia kontenera.
    * Profile zamknięcia kontenera określają, co się dzieje podczas zamykania kontenera. Można skonfigurować wiele profili zamknięcia kontenera.       
2. Kliknij przycisk Nowy.
3. W polu Identyfikator profilu zamknięcia kontenera wpisz wartość.
4. Wypełnij pole Opis.
5. W polu Manifest wybierz opcję.
    * Umożliwia określenie, czy generowanie manifestu będzie następowało podczas zamykania kontenerów czy podczas potwierdzania wysyłki. Należy zwrócić uwagę, że funkcja tworzenia manifestów wymaga obecności funkcji zarządzania transportem. Aby tworzenie manifestów działało, musi być zaimplementowane w aparatach transportu.  
6. W polu Magazyn wprowadź lub wybierz wartość.
7. W polu Domyślna lokalizacja końcowej wysyłki wprowadź lub wybierz wartość.
    * Będzie to lokalizacja, do której będą przenoszone produkty po zamknięciu kontenerów. Ta lokalizacja musi mieć zdefiniowany profil lokalizacji w parametrach magazynu.  
8. W polu Jednostka wagi wprowadź lub wybierz wartość.
9. Kliknij przycisk Zapisz.


