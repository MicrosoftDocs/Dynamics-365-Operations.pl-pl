---
title: Konfigurowanie opłat za usługi dodatkowe centrum i danych głównych usług dodatkowych
description: W tej procedurze pokazano sposób tworzenia danych głównych usług dodatkowych dla centrum oraz użycia tych danych do utworzenie opłaty za usługi dodatkowe centrum.
author: Henrikan
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSCarrierAccessorial,TMSAccessorialMaster, TMSHubAccessorial
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f1480dec82912d547bde5db614703164e3f8451c
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576239"
---
# <a name="set-up-hub-accessorial-charges-and-accessorial-masters"></a>Konfigurowanie opłat za usługi dodatkowe centrum i danych głównych usług dodatkowych

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano sposób tworzenia danych głównych usług dodatkowych dla centrum oraz użycia tych danych do utworzenie opłaty za usługi dodatkowe centrum. Procedura wykorzystuje zestaw danych firmy USMF. Konfiguracji zazwyczaj dokonuje koordynator transportu.


## <a name="set-up-a-hub-master"></a>Ustawianie głównego centrum
1. Wybierz kolejno opcje Zarządzanie transportem > Ustawienia > Ocena > Główne usługi dodatkowe.
2. Kliknij przycisk Nowy.
3. W polu Główne dodatkowe usługi wpisz wartość.
4. W polu Nazwa wpisz wartość.
5. W polu Typ dodatkowych usług wybierz opcję „Centrum”.
6. Kliknij przycisk Zapisz.
7. Zamknij stronę.

## <a name="set-up-a-hub-accessorial-charge"></a>Konfigurowanie opłaty za usługi dodatkowe centrum
1. Wybierz kolejno opcje Zarządzanie transportem > Ustawienia > Ocena > Opłaty współpracownika centrum.
2. Kliknij przycisk Nowy.
3. W polu Identyfikator współpracownika centrum wpisz wartość.
4. W polu Centrum kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
5. Na liście znajdź i zaznacz odpowiedni rekord.
6. W polu Pozycja centrum wybierz opcję.
    * Opłatę można utworzyć za odbiór lub dostawę. W zależności od wybranej opcji opłata będzie stosowana do odpowiedniego segmentu transportu na trasie.  
7. W polu Główne dodatkowe usługi kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
8. Na liście kliknij łącze w wybranym wierszu.
    * Wybierz utworzone właśnie dane główne.  
9. Kliknij przycisk Zapisz.
10. Zamknij stronę.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]