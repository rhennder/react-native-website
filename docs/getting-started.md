import React from "react";
import { View, Text, Image, TouchableOpacity } from "react-native";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { MapPin, Heart, X } from "lucide-react";

const mockProfile = {
  name: "Camila, 24",
  bio: "Amo café, viagens e boas conversas.",
  location: "2km de distância",
  photo: "https://images.unsplash.com/photo-1603415526960-f7e0328f7d1f?fit=crop&w=800&q=80"
};

export default function NearbyMatchApp() {
  return (
    <View className="flex-1 items-center justify-center bg-pink-50 p-4">
      <Card className="w-full max-w-md rounded-2xl shadow-lg">
        <Image source={{ uri: mockProfile.photo }} className="w-full h-96 rounded-t-2xl" />
        <CardContent className="p-4">
          <Text className="text-xl font-bold">{mockProfile.name}</Text>
          <Text className="text-base text-gray-600 mt-1">{mockProfile.bio}</Text>
          <View className="flex-row items-center mt-2">
            <MapPin size={16} className="text-pink-500 mr-1" />
            <Text className="text-sm text-gray-500">{mockProfile.location}</Text>
          </View>
        </CardContent>
      </Card>

      <View className="flex-row justify-around w-full max-w-md mt-6">
        <TouchableOpacity className="bg-red-100 p-4 rounded-full">
          <X size={28} className="text-red-500" />
        </TouchableOpacity>
        <TouchableOpacity className="bg-green-100 p-4 rounded-full">
          <Heart size={28} className="text-green-500" />
        </TouchableOpacity>
      </View>

      <Button className="mt-8 w-full max-w-md bg-pink-500 text-white rounded-xl">
        Abrir Chat
      </Button>
    </View>
  );
}
