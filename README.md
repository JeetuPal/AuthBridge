# AuthBridge
Demo android app for MVP,RxJava, Mokito, TDD
================
New app checklist:
colors  done
styles  done

package stucture (package by components)
Ui for 
      - login
      - createaccount
      - profilePage
      - data (service layer.)
      
MVP cluster:
View
Presenter
Model
Contract

Components:
Activity ( for initializing things)
Fragment ( Ui things)
Presenter ( controls the Logic of App and communicates b/w Model & View)
Contract 

xml ids naming convention
cont, root
first 3 letter e.g pro_component_discription(view)


product flovours: when Testing we get mock service without changing the code.
//  =========================================
Todays agenda:
Mock and production build variants (Gradle) - done.
Write Fragment (View) - 
Contract (communication channel b/w view & Presenter)
write Activities

                  Build types
Goal 2 different source sets or build variant.
Mock : Fake version of service layer. ( to test app logic i.e presenter and Model bcz i dont wanna test api & 3rd party it means whatever the service return my presenter must work properly.).
prod : Real version of service layer.

Build Variant is combination of "buildTypes" and "buildVariants"
e.g   This code snipit says dont generate release-mock sorce set.
android.variantFilter { variant ->
            if (variant.buildType.name.equals('release')
                    && variant.getFlavors().get(0).name.equals('mock')) {
                variant.setIgnore(true);
            }
        }
      
