//
//  ContentView.swift
//  Rock, Papper, Sisers challange
//
//  Created by Link, Ty - Student on 10/2/24.
//

import SwiftUI

struct ContentView: View {
    
    @State var test = "200"
    
    @State var rock = "rock"
    @State var paper = "paper"
    @State var scissors = "scissors"
    
    @State var PlayerChoise1 = "Rock"
    @State var PlayerImage = ""
    @State var PlayerScore = ""
    
    @State var CPUScore = ""
    @State var CPUChoise = "100"
    @State var CPUImage = ""
    
    var choices = ["rock", "paper", "scissors"]
    let imagesChoices = ["Rock", "Paper", "Scissors"]
    
    var body: some View {
        VStack() {
            Text("Rock, Paper, Scissors")
                .font(.largeTitle)
        }
        Spacer()
        HStack(spacing: 200) {
            Button(action: {
                chooseCPU()
            }, label: {
                Image(CPUImage)
                    .resizable()
                    .aspectRatio(contentMode: .fit)
                    .frame(width: 200, height: 200)
            })
                .font(.largeTitle)
            Text("tie")
                .font(.largeTitle)
            Button(action: {
                choosePlayer()
                
            }, label: {
                Image(CPUImage)
                    .resizable()
                    .aspectRatio(contentMode: .fit)
                    .frame(width: 200, height: 200)
            })
                .font(.largeTitle)
        }
        Spacer()
        HStack(spacing: 100) {
                Button(action: {
                   PlayerChoise1 = "rock"
                  choosePlayer()
                }, label: {
                    Image("Rock")
                        .resizable()
                        .aspectRatio(contentMode: .fit)
                        .frame(width: 100, height: 100)
                        .background(.blue)
                })
                
                Button(action: {
                    PlayerChoise1 = "paper"
                    choosePlayer()
                }, label: {
                    Image("Paper")
                        .resizable()
                        .aspectRatio(contentMode: .fit)
                        .frame(width: 100, height: 100)
                        .background(.yellow)
                })
                .padding()
                Button(action: {
                    PlayerChoise1 = "scissors"
                    choosePlayer()
                }, label: {
                    Image("Scissors")
                        .resizable()
                        .aspectRatio(contentMode: .fit)
                        .frame(width: 100, height: 100)
                        .background(.green)
                })

            }
        
        
            }
    func chooseCPU() {
        CPUChoise = choices.randomElement() ?? "rock"
        CPUImage = CPUChoise.capitalized
    }
    
    func choosePlayer() {
        PlayerChoise1 = choices ?? "rock"
        PlayerImage = PlayerChoise1.capitalized
    }
}
#Preview {
    ContentView()
}
