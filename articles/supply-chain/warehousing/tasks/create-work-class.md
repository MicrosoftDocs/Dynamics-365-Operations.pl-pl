---
title: Tworzenie klasy roboczej
description: W tej procedurze pokazano sposób konfigurowania klasy pracy.
author: ShylaThompson
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorkClass
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: be2c037ccc8f5cafc94d9fdee9647605889d0599
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830985"
---
# <a name="create-a-work-class"></a>Tworzenie klasy roboczej

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano sposób konfigurowania klasy pracy. Klas pracy są używane do kierowania i/lub ograniczania typów wierszy zlecenia, które pracownik magazynu może przetwarzać na urządzeniu przenośnym. Wiersze, które pracownik może przetwarzać, zależą od klas pracy w elementach menu urządzenia przenośnego, do których pracownik magazynu ma dostęp, oraz od klasy pracy określonej w wierszach pracy. Klas pracy mogą służyć także do sprawdzania poprawności lokalizacji odłożenia dla wiersza zlecenia. Można wykonać tę procedurę przy użyciu danych firmy demonstracyjnej USMF lub własnych danych. Ta procedura jest przeznaczona dla kierownika magazynu.

1. Wybierz kolejno opcje Zarządzanie magazynem > Ustawienia > Praca > Klasy robocze.
2. Kliknij przycisk Nowy.
3. W polu Identyfikator klasy roboczej wpisz wartość.
4. Wypełnij pole Opis.
5. W polu Typ zlecenia wybierz opcję.
6. Kliknij przycisk Nowy.
7. W polu Typ lokalizacji wpisz wartość.
    * Jeśli wybrano typ lokalizacji, tworzy to ograniczenie dotyczące tego, gdzie można odkładać towary po pobraniu. To ustawienie jest używane, gdy dyrektywa lokalizacji próbuje rozpoznać lokalizację lub gdy pracownik magazynu ręcznie podaje lokalizację w elemencie menu urządzenia przenośnego.  
8. Zamknij stronę.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]