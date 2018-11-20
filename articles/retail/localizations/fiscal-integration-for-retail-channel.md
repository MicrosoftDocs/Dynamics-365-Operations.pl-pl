---
title: "Integracja fiskalna dla kanału detalicznego"
description: "W tym temacie zawarto ogólne informacje o integracji fiskalnej w aplikacji Retail POS."
author: josaw
manager: annbe
ms.date: 11/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: v-kikozl
ms.search.validFrom: 2018-11-1
ms.dyn365.ops.version: 8.1.1
ms.translationtype: HT
ms.sourcegitcommit: 0450326dce0ba6be99aede4ebc871dc58c8039ab
ms.openlocfilehash: c852d095505abecbd44d29e9e7b53875e9069def
ms.contentlocale: pl-pl
ms.lasthandoff: 11/01/2018

---
# <a name="fiscal-integration-for-retail-channel"></a>Integracja fiskalna dla kanału detalicznego

[!include [banner](../includes/banner.md)]

W tym temacie przedstawiono omówienie funkcji integracji fiskalnej dostępnych w aplikacji Microsoft Dynamics 365 for Retail. Funkcjonalność integracji fiskalnej to struktura zapewniająca obsługę lokalnych przepisów podatkowych, które mają na celu zapobieganie nadużyciom finansowym w branży handlu detalicznego. Oto kilka typowych scenariuszy wykorzystania funkcji integracji fiskalnej:

- Wydrukowanie paragonu fiskalnego i wręczenie go klientowi.
- Zabezpieczenie przesyłania informacji o sprzedaży i zwrotach dokonanych w punkcie sprzedaży do zewnętrznego systemu urzędowego.
- Stosowanie mechanizmu ochrony danych z podpisami cyfrowymi autoryzowanymi przez urząd.

W tym temacie zawarto wytyczne dotyczące konfigurowania funkcji integracji fiskalnej, tak aby użytkownicy mogli wykonywać następujące zadania. 

- Konfigurowanie łączników fiskalnych, czyli urządzeń lub usług fiskalnych używanych do celów rejestracji fiskalnej, takich jak operacje zapisywania, składania podpisów cyfrowych i bezpiecznego przesyłania danych fiskalnych.
- Konfigurowanie dostawcy dokumentów, który określa metodę wyprowadzania danych oraz algorytm generowania dokumentów fiskalnych.
- Konfigurowanie procesu rejestracji fiskalnej, który określa kolejność etapów oraz grupę łączników używanych na każdym etapie.
- Przypisywanie procesów rejestracji fiskalnej do profili funkcji punktu sprzedaży.
- Przypisywanie profili technicznych łączników do profili sprzętowych (w przypadku lokalnych łączników fiskalnych) lub profili funkcji punktu sprzedaży (w przypadku innych typów łączników fiskalnych).

## <a name="fiscal-integration-execution-flow"></a>Proces tworzenia integracji finansowej
Poniższy scenariusz pokazuje typowy proces tworzenia integracji finansowej.

1. Zainicjowanie procesu rejestracji fiskalnej.
  
   Po wykonaniu pewnych czynności, w których jest wymagana rejestracja fiskalna, na przykład po zawarciu transakcji sprzedaży detalicznej, proces rejestracji fiskalnej jest kojarzony z bieżącym profilem funkcji punktu sprzedaży.

1. Wyszukanie łącznika fiskalnego.
   
   Dla każdego etapu rejestracji fiskalnej w procesie rejestracji fiskalnej system znajduje pasujące łączniki fiskalne podane na liście. Te łączniki mają profile funkcjonalności należące do podanej grupy łączników z listą łączników, które mają profile techniczne skojarzone z bieżącym profilem sprzętowym (tylko dla typu łącznika **Lokalny**) lub z bieżącym profilem funkcji punktu sprzedaży (dla innych typów łączników).
   
1. Wykonanie integracji fiskalnej.

   System wykonuje wszystkie niezbędne czynności zdefiniowane przez zestaw połączony ze znalezionym łącznikiem. Odbywa się to zgodnie z ustawieniami profilu funkcjonalności i profilu technicznego znalezionymi na poprzednim etapie dla tego łącznika.

## <a name="setup-needed-before-using-fiscal-integration"></a>Konfiguracja wymagana przed wykonaniem integracji fiskalnej
Przed użyciem funkcji integracji fiskalnej należy zdefiniować następujące ustawienia:

- Zdefiniuj numerację na stronie **Parametry sieci sprzedaży** dla fiskalnego profilu funkcjonalności.
  
- Określ numeracje na stronie **Wspólne parametry sieci sprzedaży** dla następujących odwołań:
  
  - Identyfikator fiskalnego profilu technicznego
  - Identyfikator grupy łącznika fiskalnego
  - Identyfikator procesu rejestracji

- Utwórz **łącznik fiskalny** w oknie **Handel detaliczny > Ustawienia kanału > Integracja fiskalna > Łączniki fiskalne** dla każdego urządzenia lub usługi, których planujesz używać na potrzeby integracji fiskalnej.

-  Utwórz **dostawcę dokumentów fiskalnych** w oknie **Handel detaliczny > Ustawienia kanału > Integracja fiskalna > Dostawcy dokumentów fiskalnych** dla wszystkich łączników fiskalnych. Mapowanie danych jest uważane za element dostawcy dokumentów fiskalnych. Aby skonfigurować inne mapowania danych dla tego samego łącznika (np. do obsługi szczególnych przepisów stanowych), należy utworzyć innych dostawców dokumentów fiskalnych.

- Utwórz **profil funkcjonalności łącznika** w oknie **Handel detaliczny > Ustawienia kanału > Integracja fiskalna > Profile funkcjonalności łącznika** dla każdego dostawcy dokumentów fiskalnych.
  - Nazwij łącznik.
  - Wybierz dostawcę dokumentów.
  - Określ ustawienia stawek podatku VAT na karcie **Ustawienia usługi**.
  - Określ mapowanie kodów podatku VAT i mapowanie typów metod płatności na karcie **Mapowanie danych**.

  #### <a name="examples"></a>Przykłady 

  |  | Format | Przykład | 
  |--------|--------|--------|
  | Ustawienia stawek podatku VAT | wartość : VATrate | 1 : 2000, 2 : 1800 |
  | Mapowanie kodów VAT | VATcode : wartość | vat20 : 1, vat18 : 2 |
  | Mapowanie typów metod płatności | TenderTyp : wartość | Gotówka : 1, Karta : 2 |

- Utwórz **grupę łączników fiskalnych** w oknie **Handel detaliczny > Ustawienia kanału > Integracja fiskalna > Grupa łącznika fiskalnego**. Grupa łączników to podzbiór profili funkcjonalności połączonych z łącznikami fiskalnymi, które wykonują te same funkcje i są używane na tym samym etapie procesu rejestracji fiskalnej.

   - Dodaj profile funkcjonalności do grupy łączników. Kliknij przycisk **Dodaj** na stronie **Profile funkcjonalności** i wybierz numer profilu.
   - Jeśli chcesz zawiesić używanie profilu funkcjonalności, w ustawieniu **Wyłącz** zaznacz wartość **Tak**. 
   
     Ta zmiana dotyczy tylko bieżącej grupy łączników. Możesz kontynuować używanie tego samego profilu funkcjonalności w innych grupach łączników.

     >[!NOTE]
     > Wewnątrz grupy łączników każdy łącznik fiskalny może mieć tylko jeden profil funkcjonalności.

- Utwórz **profil techniczny łącznika** w oknie **Handel detaliczny > Ustawienia kanału > Integracja fiskalna > Profile techniczne łącznika** dla każdego łącznika fiskalnego.
  - Nazwij łącznik.
  - Wybierz typ łącznika: 
      - **Lokalny** — ustaw ten typ dla fizycznych urządzeń lub aplikacji zainstalowanych na komputerze lokalnym.
      - **Wewnętrzny** — ustaw ten typ dla urządzeń fiskalnych i usług połączonych z aplikacją Retail Server.
      - **Zewnętrzny** — dla zewnętrznych usług obrachunkowych, takich jak portal internetowy udostępniony przez urząd skarbowy.
    
  - Określ ustawienia na karcie **Połączenie**.

      
 >[!NOTE]
 > Dla profili technicznych i funkcjonalności zostanie załadowana zaktualizowana wersja załadowanej wcześniej konfiguracji. Jeśli odpowiedni łącznik lub dostawca dokumentów jest już używany, otrzymasz o tym powiadomienie. Domyślnie wszystkie zmiany wprowadzone ręcznie w profilach funkcjonalności i technicznych zostaną zachowane. Aby zastąpić te profile domyślnym zestawem parametrów z konfiguracji, kliknij przycisk **Aktualizuj** na stronach **Profile funkcjonalności łącznika** i **Profile techniczne łącznika**.
 
- Utwórz **proces rejestracji fiskalnej** w oknie **Handel detaliczny > Ustawienia kanału > Integracja fiskalna > Procesy rejestracji fiskalnych** dla każdego unikatowego procesu integracji fiskalnej. Proces rejestracji jest definiowany przez sekwencję etapów rejestracji oraz przez grupę łączników używaną na każdym etapie. 
  
  - Dodaj etapy rejestracji do procesu:
      - Kliknij przycisk **Dodaj**.
      - Wybierz typ łącznika.
      
      >[!NOTE]
      > To pole określa, gdzie system będzie szukał profilu technicznego łącznika — albo w profilach sprzętowych (łącznik typu **Lokalny)**, albo w profilach funkcji punktu sprzedaży (wszystkie pozostałe typy łączników fiskalnych).
      
   - Wybierz grupę łączników.
   
     >[!NOTE]
     > Kliknij przycisk **Sprawdź poprawność**, aby sprawdzić integralność struktury procesu rejestracji. Zaleca się przeprowadzanie weryfikacji w następujących przypadkach:
       >- W nowym procesie rejestracji po skonfigurowaniu wszystkich ustawień, w tym po utworzeniu powiązań z profilami funkcji punktu sprzedaży i profilami sprzętowymi.
       >- Po dokonaniu zmian w istniejącym procesie rejestracji.

-  Powiąż procesy rejestracji fiskalnej z profilami funkcji punktu sprzedaży w oknie **Handel detaliczny > Ustawienia kanału > Ustawienia punktu sprzedaży > Profile punktu sprzedaży > Profile funkcji**.
   - Kliknij przycisk **Edytuj** i wybierz opcję **Identyfikator procesu** na karcie **Proces rejestracji fiskalnej**.
- Powiąż profile techniczne łączników z profilami sprzętowymi w oknie **Handel detaliczny > Ustawienia kanału > Ustawienia punktu sprzedaży > Profile punktu sprzedaży > Profile sprzętu**.
   - Kliknij przycisk **Edytuj**, a następnie kliknij przycisk **Nowy** na karcie **Fiskalny profil techniczny**.
   - Wybierz profil techniczny łącznika w polu **Identyfikator profilu**.
   
     >[!NOTE]
     > Do profilu sprzętowego można dodać kilka profili technicznych. Jednak nie jest to obsługiwane, jeśli profil sprzętowy ma więcej niż jedno przecięcie z którąkolwiek grupą łączników. Aby uniknąć nieprawidłowych ustawień, zalecamy sprawdzenie poprawności procesu rejestracji po zaktualizowaniu wszystkich profili sprzętowych.

