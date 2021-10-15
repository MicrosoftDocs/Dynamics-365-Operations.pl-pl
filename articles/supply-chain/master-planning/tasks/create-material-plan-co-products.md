---
title: Tworzenie planu materiałów dla produktów towarzyszących
description: Planista produkcji planuje zapotrzebowania materiałowe na zapasy, które są produktami towarzyszącymi formuły.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: deae0d7e0295aa02f5ad512f67e9e3d2148c2e33
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7578303"
---
# <a name="create-a-material-plan-for-co-products"></a>Tworzenie planu materiałów dla produktów towarzyszących

[!include [banner](../../includes/banner.md)]

Planista produkcji planuje zapotrzebowania materiałowe na zapasy, które są produktami towarzyszącymi formuły. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USP2.

## <a name="create-requirement-for-a-co-product"></a>Tworzenie zapotrzebowania na produkt towarzyszący

1. Przejdź do lokalizacji **Sprzedaż i marketing \> Obszary robocze \> Przetwarzanie zamówienia sprzedaży i zapytania o nie**.
1. Wybierz pozycję **Nowy**.
1. Wybierz opcję **Zamówienie sprzedaży**.
1. W polu **Konto odbiorcy** wpisz wartość.
    * Przykład: US-001  
1. Kliknij przycisk **OK**.
1. W polu **Numer towaru** wpisz wartość.
    * Przykład: P6003  
1. W polu **Ilość** wpisz liczbę.
    * Przykład: 50000  
1. Wybierz opcję **Zapisz**.

## <a name="create-a-material-plan-for-co-products"></a>Tworzenie planu materiałów dla produktów towarzyszących

1. Zamknij stronę.
1. Zamknij stronę.
1. Wybierz opcję **Planowanie główne**.
1. W polu **Plan** wybierz przycisk rozwijany, aby otworzyć wyszukiwanie.
1. Na liście wybierz łącze w wybranym wierszu.
    * Przykład: Plan główny  
1. Wybierz opcję **Uruchom**.
1. Rozwiń lub zwiń sekcję **Rekordy do uwzględnienia**.
1. Wybierz **Filtry**.
1. Na liście zaznacz wiersz, gdzie **Pole** = *Numer towaru*.
1. W polu **Kryteria** wpisz wartość.
    * Przykład: P6003  
1. Kliknij przycisk **OK**.
1. Kliknij przycisk **OK**.
1. Wybierz **Zamówienia planowane**.
1. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład ustaw filtr na pole **Numer towaru** z wartością 'P6000'.
    * Wyfiltruj według towaru formuły będącego produktem towarzyszącym towaru, dla którego utworzono zamówienie sprzedaży.  
1. Na liście oznacz wybrany wiersz.
    * Wybierz dowolny wiersz zwrócony przez filtr.  
1. Na liście wybierz łącze w wybranym wierszu.
1. Rozwiń sekcję **Oznaczanie transakcji**.
1. Na liście wybierz łącze w wybranym wierszu.
    * Zamówienie planowane jest kojarzone z zamówieniem sprzedaży na produkt towarzyszący.  
1. Zamknij stronę.

## <a name="create-a-second-requirement-for-a-co-product"></a>Tworzenie drugiego zapotrzebowania na produkt towarzyszący

1. Przejdź do lokalizacji **Sprzedaż i marketing \> Obszary robocze \> Przetwarzanie zamówienia sprzedaży i zapytania o nie**.
1. Wybierz pozycję **Nowy**.
1. Wybierz opcję **Zamówienie sprzedaży**.
1. W polu **Konto odbiorcy** wpisz wartość.
    * Przykład: US-001  
1. Kliknij przycisk **OK**.
1. W polu **Numer towaru** wpisz wartość.
    * Przykład: P6003  
1. W polu **Ilość** wpisz liczbę.
    * Przykład: 50000  
1. Wybierz opcję **Zapisz**.

## <a name="create-a-second-material-plan-for-co-products"></a>Tworzenie drugiego planu materiałów dla produktów towarzyszących

1. W polu **Plan** wybierz przycisk rozwijany, aby otworzyć wyszukiwanie.
2. Na liście wybierz łącze w wybranym wierszu.
    * Przykład: Plan główny  
3. Wybierz opcję **Uruchom**.
4. Rozwiń lub zwiń sekcję **Rekordy do uwzględnienia**.
5. Wybierz **Filtry**.
6. Na liście zaznacz wiersz, gdzie **Pole** = *Numer towaru*.
7. W polu *Kryteria* wpisz wartość.
    * Przykład: P6003  
8. Kliknij przycisk **OK**.
9. Kliknij przycisk **OK**.
10. Wybierz **Zamówienia planowane**.
11. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład ustaw filtr na pole **Numer towaru** z wartością 'P6000'.
    * Wyfiltruj według towaru formuły będącego produktem towarzyszącym towaru, dla którego utworzono zamówienie sprzedaży.  
12. Na liście oznacz wybrany wiersz.
    * Wybierz dowolny wiersz zwrócony przez filtr.  
13. Na liście wybierz łącze w wybranym wierszu.
14. Rozwiń lub zwiń sekcję **Oznaczanie transakcji**.
15. Na liście wybierz łącze w wybranym wierszu.
    * Zamówienie planowane jest kojarzone z zamówieniem sprzedaży na produkt towarzyszący.  
16. Zamknij stronę.
17. Wybierz opcję **Planowanie główne**.
18. Wybierz kolejno opcje **Planowanie główne \> Ustawienia \> Parametry planowania głównego**.
19. W polu **Wyłącz wszystkie procesy planowania** wybierz opcję *Nie*.
20. Zamknij stronę.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]