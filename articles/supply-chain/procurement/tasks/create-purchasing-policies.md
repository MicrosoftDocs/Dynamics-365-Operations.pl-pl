--- 
title: "Tworzenie zasad zakupów"
description: "W tej procedurze pokazano sposób tworzenia zasad zakupów dopasowanych do procesów biznesowych w obszarze zakupów."
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c2b3a66443394f5bfbe51b6685513281025d68fd
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="create-purchasing-policies"></a>Tworzenie zasad zakupów

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób tworzenia zasad zakupów dopasowanych do procesów biznesowych w obszarze zakupów. Zanim będzie można utworzyć zasady dotyczące zakupów, należy skonfigurować parametry zasad zakupów, . Można tworzyć, modyfikować i wycofywać zasady zakupów, ale nie można usunąć zasady zakupów. Tę procedurę zazwyczaj wykonuje kierownik ds. zakupów. Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych.


## <a name="set-up-policy-parameters"></a>Ustawianie parametrów zasad
1. Przejdź do okna Zasady zakupów.
2. Kliknij opcję Parametry.
    * Reguły pierwszeństwa zasad dotyczą różnych poziomów w organizacji. Wyświetlane jednostki organizacyjne zależą od hierarchii organizacyjnej oraz od tego, na których poziomach w hierarchii przypisano cel Wewnętrzna kontrola zaopatrzenia. Na przykład w organizacji mogą istnieć firmy, centra kosztów, regiony i działy, ale tylko niektóre z nich mogą mieć w hierarchii cel Wewnętrzna kontrola zaopatrzenia. Domyślnie jest dostępna organizacja typu Firma.  
3. Kliknij kartę Parametry typu reguły.
4. W drzewie zaznacz element „Zasady zakupów\Reguła kontroli zapotrzebowania na zakup”.
    * Należy zdefiniować kolejność pierwszeństwa dla stosowania zasad na poziomie zasad. Jednak w przypadku niektórych typów zasad, można zastąpić kolejność pierwszeństwa dla poszczególnych typów reguł dotyczących zasad. Na przykład można zdefiniować pierwszeństwo zasad zakupów w następującej kolejności: centrum kosztów, dział, firma. Jednak dla reguły dotyczącej katalogów chcesz, aby pierwszeństwo było następujące: dział, centrum kosztów, firma. Istnieje możliwość zmiany pierwszeństwa dla reguły dotyczącej katalogu. Gdy pracownik tworzy zapotrzebowanie, wyświetlany katalog zależy od zasad, które są skojarzone najpierw z działem pracownika, następnie z centrum kosztów, a na końcu z firmą.  
    * Jeśli jest wyświetlany więcej niż jeden poziom organizacyjny, można strzałkami w górę/w dół ustawić pierwszeństwo dla reguły kontroli zapotrzebowania na zakup.  
5. Zamknij stronę.

## <a name="create-a-new-policy"></a>Utwórz nowe zasady
1. Kliknij przycisk Nowy.
2. W polu Nazwa wpisz wartość.
3. Wypełnij pole Opis.
    * Pojedyncza zasada zakupów może stosować się tylko dla jednej hierarchii organizacyjnej. Na przykład możesz mieć jedną hierarchię o nazwie „Położenie geograficzne” i jedną o nazwie „dział” i dla każdej ustawić inną zasadę zakupów.  
    * Wybierz organizację, do której ma być stosowana zasada.  
4. Kliknij strzałkę, aby dodać wybraną organizację.
    * Można powtórzyć ten proces, aby dodać więcej organizacji.  

## <a name="add-a-policy-rule"></a>Dodawanie reguły
1. Na liście Typ reguły zaznacz element Reguła celu zapotrzebowania.
    * Utworzysz regułę, która ustawia domyślny cel zapotrzebowania na typ Zużycie, ale za to pozwala wybrać typ uzupełniania zapasów.  
2. Kliknij przycisk Utwórz regułę.
3. W polu Zezwalaj na zastępowanie ręczne wybierz opcję Tak.
4. Kliknij przycisk Zamknij.
    * Teraz można skonfigurować inne reguły dla zasady zakupów.   Należy zauważyć, że typ reguły nie może określać nakładających się reguł, które są aktywne w tym samym czasie w jednej zasadzie zaopatrzenia.  
5. Zamknij stronę.
6. Zamknij stronę.


