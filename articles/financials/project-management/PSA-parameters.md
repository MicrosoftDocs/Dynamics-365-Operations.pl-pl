---
title: Parametry integracji aplikacji Project Service Automation
description: "Można skonfigurować, jak mają być domyślnie wyświetlane dane podczas integrowania rozwiązania Project Service Automation z Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 12/13/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: 32f7f70c5b1071cef5a3360ccc09fa2d95fbf9a9
ms.contentlocale: pl-pl
ms.lasthandoff: 05/29/2018

---

# <a name="project-service-automation-integration-parameters"></a>Parametry integracji aplikacji Project Service Automation

Na stronie **Parametry integracji aplikacji Project Service Automation** można skonfigurować domyślnie zachowanie danych podczas integrowania aplikacji Project Service Automation z aplikacją Finance and Operations. Następujące ustawienia należy skonfigurować w celu pomyślnej synchronizacji projektów z rozwiązania Project Service Automation w Finance and Operations.

> [!NOTE]
> Mechanizmy integracji zadań projektu, kategorii transakcji wydatkowych, szacunków godzin, szacunków wydatków i blokowania funkcji są dostępne w programie Dynamics 365 for Finance and Operations w wersji 8.0.




| **Karta**                      | **Field**                          | **Opis**                    |
|------------------------------|------------------------------------|--------------------------------|
| **Ogólne**                  | **Domyślny typ projektu**               | W ustawieniu **Typ projektu** wybierz wartości domyślną, czyli tę, która powoduje synchronizowanie projektów z aplikacji Project Service Automation, jeśli nie podano wartości domyślnej w szablonie integracji. Podczas synchronizacji nowe projekty będą miały parametr **Typ projektu** ustawiony na tę wartość i mogą być aktualizowane, gdy wiersze umowy na projekt są synchronizowane z programu Project Service Automation.               |
| **Ogólne**                  | **Kategoria czasu**                      | W ustawieniu **Kategoria czasu** wybierz wartość domyślną, czyli tę, która powoduje synchronizowanie szacunków godzin z aplikacji Project Service Automation. Podczas synchronizacji nowe prognozy godzin w projekcie w programie Finance and Operations będą miały parametr **Kategoria** ustawiony na tę wartość, gdy wartości szacowane i rzeczywiste godzin będą synchronizowane z modułu Project Service Automation.   |
| **Ogólne**                  | **Kategoria opłat**                       | W ustawieniu **Kategoria opłat** wybierz wartość domyślną, czyli tę, która powoduje synchronizowanie wartości rzeczywistych opłat z aplikacji Project Service Automation. Podczas synchronizacji nowe transakcje opłat w programie Finance and Operations będą miały parametr **Kategoria** ustawiony na tę wartość, gdy wartości rzeczywiste opłat będą synchronizowane z modułu Project Service Automation.          |
| **Wartości domyślne grupy projektów**   | **Typ projektu** | Kliknij przycisk **Nowy** i dodaj wiersz, w którym będzie można wybrać typ projektu, dla którego będzie ustawiana domyślna grupa projektu. Konkretny typ projektu można wybrać tylko raz w konfiguracji.              
|                              | **Grupa projektów**          | Wybierz domyślną grupa projektów dla podanego typu projektu. Kiedy nowe projekty są synchronizowane w aplikacji Project Service Automation **Typ projektu** będzie wartością zależną od typu projektu, jeśli nie podano wartości domyślnej w szablonie integracji.  |
| **Ustawienia domyślne typu fakturowania**    | **Typ fakturowania** | Kliknij przycisk **Nowy** i dodaj wiersz, w którym będzie można wybrać typ fakturowania, dla którego będzie ustawiana domyślna właściwość wiersza. Konkretny typ fakturowania można wybrać tylko raz w konfiguracji.          |
|                              | **Właściwość wiersza**| Wybierz domyślną właściwość wiersza dla podanego typu fakturowania. Gdy nowe szacunkowe godziny, nowe szacunki wydatków lub nowe wartości rzeczywiste są synchronizowane z aplikacji Project Service Automation, wartość **Właściwość wiersza** domyślna zależy typu fakturowania.          |
| **Blokowanie funkcji**    |                   | Wybierz funkcje, które w programie Finance and Operations mają zostać wyłączone dla projektów i umów pochodzących z modułu Project Service Automation. Na przykład można wyłączyć możliwość edytowania umów i projektów, tworzyć struktury podziału pracy oraz wypełniać kart czasu pracy w programie Finance and Operations. Pola związane z księgowaniem nadal będą włączone, nawet jeśli ustawienie parametru spowodowało, że są niedostępne. Domyślnie wszystkie funkcje zostaną włączone.           |

