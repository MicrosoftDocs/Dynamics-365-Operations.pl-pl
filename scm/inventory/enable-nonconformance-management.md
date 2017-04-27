---
title: "Zarządzanie niezgodnościami"
description: "W tym artykule opisano podstawową konfigurację niezbędną do korzystania z funkcji niezgodności. Dodatkowe ustawienia są potrzebne do używania zleceń kontroli jakości."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventParameters, InventProblemType, InventProblemTypeSetup, InventQuarantineZone, InventTestDiagnosticType, InventTestReportSetup, SysUserManagement
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 28951
ms.assetid: a62d4ba8-eebc-4b14-b587-630be7298522
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 6f25e2930ff265df1f938cdf56e8a0f4993617af
ms.lasthandoff: 03/31/2017


---

# <a name="nonconformance-management"></a>Zarządzanie niezgodnościami

[!include[banner](../includes/banner.md)]


W tym artykule opisano podstawową konfigurację niezbędną do korzystania z funkcji niezgodności. Dodatkowe ustawienia są potrzebne do używania zleceń kontroli jakości. 

Aby włączyć zarządzanie niezgodnościami, wykonaj następujące kroki:

1.  Zdefiniuj parametry Zarządzanie zapasami i magazynem związane z niezgodnościami.
    -   W opcji **Korzystaj z funkcji zarządzania jakością** wybierz wartość **Tak**.
    -   W polu **Stawka godzinowa** wpisz stawkę godzinową pracy w walucie lokalnej. Stawka godzinowa używana jest do obliczania kosztów operacji związanych z niezgodnością. Stawka godzinowa i obliczone koszty dostarczają informacji pomocniczych o niezgodności. Nie mają one styczności z innymi funkcjami.
    -   Użyj karty **Zarządzanie jakością** na stronie **Konfiguracja raportu**, aby zdefiniować typ dokumentu do wydrukowania. Można wydrukować raport o niezgodności, znacznik niezgodności lub raport korekty. Możesz zdefiniować więcej niż jeden rekord w celu drukowania różnych typów dokumentów w raporcie lub drukowania notatek wewnętrznych i zewnętrznych. Strona **Typ dokumentu** może być pomocna przy definiowaniu unikatowego typu dokumentu dla niezgodności i unikatowego typu dokumentu dla korekty. Załóżmy, że chcesz wpisywać notatki dotyczące niezgodności za pomocą unikatowego typu dokumentu dla niezgodności. W takim przypadku zidentyfikuj unikatowy typ dokumentu w opcjach raportu.
    -   Włącz sekwencji numerów dla odwołania do niezgodności i korekty.

2.  Włączanie zatwierdzania niezgodności przez użytkownika. W polu **Nazwa** na stronie **Użytkownicy** przypisz pracownika do każdego użytkownika, który musi zatwierdzić niezgodność. System śledzi historię niezgodności, obserwując pracowników, którzy zmienili stan niezgodności. Użytkownik nie może zatwierdzić niezgodności, jeśli nie ma przypisanego identyfikatora pracownika.
3.  Definiowanie typów problemów, które będą przypisywane do niezgodności. Użyj strony **Typ problemu** do zdefiniowania klasyfikacji problemów z jakością, które występują w różnych typach niezgodności. Można skonfigurować następujące typy niezgodności: **Wewnętrzny**, **Odbiorca**, **Dostawca**, **Żądanie usługi**, **Produkcji** i **Wytwarzanie produktu towarzyszącego**. Użyj strony **Typy niezgodności**, do autoryzacji typu problemu, który ma być używany do obsługi co najmniej jednego typu niezgodności. Na przykład typ problemu związany z kodem wady może dotyczyć wszystkich typów niezgodności, podczas gdy typ problemu związany ze skargami odbiorców może dotyczyć tylko niezgodności typu **Odbiorca** i **Żądanie usługi**.
4.  Zdefiniuj strefy kwarantanny, aby podać wskazówki dotyczące postępowania z wadliwymi materiałami. Na stronie **Strefy kwarantanny** zdefiniuj strefy, które można przypisać do niezgodności. Wydrukowany znacznik niezgodności będzie zawierać przypisaną strefę kwarantanny wraz z informacjami użytku jako wskazówkę w postępowaniu z wadliwymi materiałami. Strefy mogą odpowiadać lokalizacjom magazynowym lub zasobom operacyjnym.
5.  Zdefiniuj typy diagnostyki przypisywane do korekty. Na stronie **Typy diagnostyki** zdefiniuj klasyfikację akcji diagnostycznych. Korekta określa jakiego rodzaju działania diagnostyczne należy podjąć w przypadku zatwierdzonej niezgodności, a także osobę, która ma to działanie wykonać. Określa również żądaną datę ukończenia żądania planowaną datę ukończenia.
6.  Zdefiniuj operacje pokrewne, które będą przypisywane do niezgodności. Za pomocą strony **Operacje** zdefiniuj klasyfikację pracy, którą można wykonać dla zatwierdzonej niezgodności. Przypisując operację pokrewną do niezgodności, można również zdefiniować szczegółowe informacje o powiązanych materiałach, godzinach robocizny i opłatach dodatkowych wymaganych do wykonania operacji. Ta informacja służy do obliczania szacowanego kosztu operacji. Informacje szczegółowe i szacowane koszty mają charakter odnośnikowy. Operacje pokrewne dla jakości różnią się od operacji, które można zdefiniować dla marszruty produkcji.


<a name="see-also"></a>Informacje dodatkowe
--------

[Tworzenie i przetwarzanie rekordu niezgodności (przewodnik po zadaniu)](https://ax.help.dynamics.com/en/wiki/create-and-process-a-nonconformance/)

[Procesy zarządzania jakością](quality-management-processes.md)

[Konfigurowanie warunków wstępnych zarządzania brakiem zgodności (przewodnik po zadaniu)](https://ax.help.dynamics.com/en/wiki/set-up-prequisites-for-nonconformance-management/)




